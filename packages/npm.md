# Node Package Management (npm / yarn)


Major_Version.Minor_Version.Patch_Version

Patch_Version : Some bug fixes with backwards compatibility

Minor_Version : Bug fixes + New features + Backward compatibility

Major_Version : There are breaking changes so test before applying this version

~ (tilde)
If dependency version has prefix ~ then it will lock the major and minor version and next time you run npm install or npm update, will install the latest patch version no matter what patch version is defined in dependency version.

Suppose if there is update in patch and version 4.2.6 is available then 4.2.6(latest) will be installed but major and minor version will be same.

^ (caret)
Dependency with ^ prefix lock the major version and install the latest minor version no matter what patch and minor version has defined in package.json

Without ~ and ^
If no prefix is defined then the same version will be installed as defined.


NOTE: a good description of how Meteor uses node, npm, and yarn...
https://github.com/meteor/meteor/issues/8493
