# Flow notes
## Intro 
* the value get from flow, or how much you like it does depend on how well you know javascript & react
    - I am novice to intermediate, still feeling pain
* one value, you learn javascript and react, the language and typing
* second value, directly prevents some errors (especially those hard to find)

## Pros 
* type checking...

## Cons
* makes language verbose, in some case less readable

## Notes 
* The better you know javascript, the easier flow will be 
    - I am still gaining understanding of intermediate / advanced topics, such as class, instances, etc.
* to add insult to injury, you can add eslint flowtype 
    - it's somewhat nice in that it integrates nicely with many editors
    - however, although configurable, it can be more strict than flow 
        + e.g., flow recognizes render, eslint flow does not, and you can't specifically suppress return type warning for just render 
    - eslint and flow can have conflicts
        + eslint react stated a method should be static, flow didn't recognize a static as an annotated property (no matter which direction you went, you would get an error -I ffm'd it.)
* there are many times I curse flow for saying I have the wrong type, and I think it's unnecessary at that line, but turns out I made a mistake
    - ie, flow complained an element didnt' have value property, I had incorrectly typed the element as an htmldivelement, which indeed does not have a value
* Ways to check or not check 
    - include or exclude flow header at top of file 
    - broad libdef or type annotation definitions: essentially wild card something (any, *)
    - ingnore next line with FlowFixMe comment
* I have had cases where it has taken 10 minutes to write working code, and over two hours to correct the flow errors. (more than once)
    - this dawned on me, when I was reading github issues, and someone else made that same comment.

## Resources

## Usage Notes 
* $FlowFixMe - suppressess a flow error message
    - https://wietse.loves.engineering/ignore-a-flowtype-error-on-a-specific-line-14cdfa70a739
