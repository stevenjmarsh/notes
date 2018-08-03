# Node Package Management (npm / yarn)


MajorVersion . MinorVersion . PatchVersion

MajorVersion : There are breaking changes so test before applying this version

MinorVersion : Bug fixes + New features + Backward compatibility

PatchVersion : Some bug fixes with backwards compatibility

## Installing / Updating Packages 

When installing npm packages, packages are typically listed in package.json with '^'. When running 'npm update' or an initial 'npm install', this facilitates updating/installing npm packages to the latest non-breaking versions.

> To install a specific version of a package, run npm install with the '@' symbol. e.g. `npm install mypackage@2.1.1`

When running `npm update` or `npm install`, packages will be installed or updated based on the following rules...

##### ~ (tilde)
If dependency version has prefix '~' then it will lock the major and minor version and next time you run npm install or npm update, will install the latest __patch version__, no matter what patch version is defined in dependency version.

##### ^ (caret)
Dependency with '^' prefix lock the major version and install the latest __minor and patch__

##### @ (or without ~ and ^)
If no prefix is defined then the same version will be installed as defined.

### Outdated Packages 
To determine which npm packages are out of date, and how they will be updated, run `npm outdated` (or `yarn outdated`).

> Outdated will list three versions for each package: current, wanted, latest.
> 'current' is the package version currently installed
> 'wanted' is the package version that would be installed when running `npm update` (based on '@', '~', '^')
> 'latest' is the latest published package version that is available



### Notes

NOTE: a good description of how Meteor uses node, npm, and yarn...
https://github.com/meteor/meteor/issues/8493

NOTE: blog post on node versions and Meteor 
