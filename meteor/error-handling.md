# Error Types

## JavaScript Error
* standard JavaScript error  (several types... RangeError, EvalError, ...)
* usage: error doesn't need to be reported to client, internal to server
```
{
    message?: string,       // optional, readable description
    fileName?: string,      // optional, filename (default of current file)
    lineNumber?: string,    // optional, line number (default of current line#)
}
```

## Meteor.Error
* https://docs.meteor.com/api/methods.html#Meteor-Error
* usage: when server not able to complete a user's desired action (ie permission)

```
{
    error: string | number,     // code that uniquely identifies kind of error
    reason?: string,            // optional, short readable summary
    details?: string,           // optional, additional info    
}
```

NOTE: if thrown on server, will send error object back to client over websocket
For methods, if any Error other than a Meteor.Error is thrown, the method will sanitize the error as a 500 Internal server error.

## ValidationError
* usage: when arguments are of wrong type, or form fields fail validation
* details defintion: https://www.npmjs.com/package/simpl-schema#manually-adding-a-validation-error 

```
constructor:
[
    {
        name: string,       // required, name of field error is about
        type: string,       // required, type of error
        others...           // optional additional info
    },
    ...
]

error fields:
{
    error: string,              // e.g "validation-error",  ~ error code
    errorType: string,          // "ClientError", "Meteor.Error"
    name: string,               // "ClientError"
    isClientSafe?: boolean,     // true
    reason?: string,            // "Validation failed"
    message?:"Validation failed [validation-error]",
    details: [
        {
            name: string,            // required, schema key name (ie username)
            value?: string,          // optional, the value that failed
            type: string,    // required, SimpleSchema.ErrorTypes or any string
            dataType?: string,       // "Number"
            min?: number,
            max?: number,
            message?: "Latitude must be of type Number"
        },
        ...
    ]
}
```

Strange: 
since adding simpleSchema validation error transform definition...
ValidationError.is() works (returns true) when checking error returned by Accounts.validateNewUser, but fails when checking error returned
by ValidatedMethod
