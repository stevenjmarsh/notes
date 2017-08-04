
## Testing
### Strategy
* Unit Testing
    * __Use Mocha & TestDouble.js__
      * for React testing, also include enzyme (and jsdom if using mount)
    * Scenarios
        * easily isolatable pure javascript
        * javascript with some dependencies (or injected dependencies)
        * pure function React components
    * __RUN:__ continuously, watch 
* Integration Testing
    * __Use Meteor Test__
    * Scenarios
        * test across unit boundaries
        * cases requiring complex or heavy use of meteor system and meteor packages
    * Examples
        * React Containers
        * calling a method, from server side (server side only code)
    * __RUN:__ possibly continuously, watch 
* Integration Testing, Full App 
    * __Use Meteor Test, --full-app__
    * Scenarios
        * test across boundaries, complex cases
        * test across client server gap
    * Examples
        * meteor method calls
        * testing UI features relying on complex / specific publications
    * __RUN:__ after some code completion, and as part of CI
* End-to-End Testing
    * __Use Chimp__
    * Scenarios
        * test features and UI
    * __RUN:__ after some code completion, and as part of CI
* Acceptance Testing
    * __TBD__ may just stick with / stop at End-to-End testing
    * __Use Chimp, with Gherkin__
    * Scenarios
        * end-to-end testing, plus requirements and feature explanation
    * __RUN:__ after some code completion (especially feature), and as part of CI

### Assertion Libraries
* Trying a few different assertion libraries, to determine a preferred
    * __Chai assert__ - nice, concise, quick to write, still readable (expect when in shortest form, like assert(something); 
        * bonus, seems a lot quicker to find / look up api in docs
    * __Chai expect__ - popular, relatively quickly to write, very reable
        * often used in examples and supporting assertion libraries
    * __chai-enzyme__ - uses expect, plus React specific convenience functions
    * __testdouble-chai__ - uses expect, adds called/calledWith convenience funtions
    
### Testing Methods & ValidatedMethods (notes)
* TL;DR - short version, in meteor test methods have a strange behavior where expections aren't pushed back to clients when calling with Meteor.call or .apply and passing a callback
    * so you must try / catch for exceptions in the passed call back, and then check return values
* The tests around Tasks methods, test a variety of scenarios. Depending on how the meteor method is call, and from where (client, server), the behaviour of the responses can vary, namely in the error conditions different exceptions are thrown
* Even though the application code only calls the methods in one manner, ValidatedMethod from the client, the other manners are tested as well to ensure they are secure
    * ie, a malicious user could call the different manners from the client console
* Variations to consider, test, and understand behaviour...
    * from the server - Method.call("setCompleted", )
    * from the client
    * using Method.call
        * with a callback
        * without a callback
    * using ValidatedMethod.call
    * using ValidatedMethod._execute (from test code)
* Each of the variations that could be used on the client were tested to understand any security vulnerabilities, and have the test fail in the event a code change exposed a vulnerability
* Each of the server side variations were done to understand behaviour, and test that code if called from the server (make sure that behaviour doesn't change with code changes)
* Had difficulty getting ASSERT to work properly when trying to test a Method.call
    * asserts were either timing out (even with done) OR not thowing / catching expections
        * this was due to them being thrown in a callback (outside of it() scope)
    * found this [forum](https://forums.meteor.com/t/how-to-test-meteor-methods/21710/11) discussion to help come up with a solution
    * also, some exceptions being thrown aren't showing up in the web reporter, which _'may'_ be due to this [issue](https://github.com/practicalmeteor/meteor-mocha/issues/11)
        * see comments there May 19 2016 and later, they mention it is specifically with Meteor methods not being able to be tested
        * the suggestion in comment 9/18/16, is what I figured out through much of my own trial and error (days).
* (TBD) Potential Security test - see if you could use ValidatedMethod._execute to set the context to some other user's Id and modify a task of theirs
    * you would need to have the other userId and taskId
    * a sample test is written (and skipped) in tasks.app-tests.js
* Wrote some tests (in tasks.tests.js) simply to learn the behavior of SimpleSchema and Factory
    * for example, is using collection2, it will clean the data and then insert it (it doesn't fail if the object doesn't pass the validation)
    * when collection2 cleans an object, it modifies the original object (does not create a new copy)
* TAKE-AWAY: if, in testing, you want to make sure your schemas and test code are up to date, consider explicitly calling validate in the test. that way if it fails, you know you need to update the schema (or Factory definition) needs to be updated
    * this is a practice of keeping Factory.define in sync with a simple schema defintion, without having to keep Factory in production code (like the Meteor Todos example)

### Notes - general
* to access the mongo shell, while running test for --full-app...
    - `mongo meteor --port 3001`
    - https://forums.meteor.com/t/hint-access-to-mongo-shell-when-testing/32621
* 
