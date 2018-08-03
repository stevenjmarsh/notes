# SimpleSchema npm package usage notes 

* npm package is the primary supported package moving forward, the atmosphere package is only updated for critical issues
* for meteor specific support (and migration from atmosphere package), see:
    - https://www.npmjs.com/package/simpl-schema#the-history-of-simpleschema
    - https://github.com/aldeed/meteor-simple-schema/blob/master/CHANGELOG.md#200
* __NOTE:__ if using SimpleSchema to __validate__ standard methods (not ValidatedMethods) and Accounts.validateNewUser, you must use defineValidationErrorTransform to throw a meteor error, in order for error detail to be passed back to client via ddp
    - https://github.com/aldeed/meteor-simple-schema/blob/master/CHANGELOG.md#200
    - frustratingly, this was NOT mentioned in the CHANGELOG

