# Various Tips

Various tips to remember when running in to build or environmental issues.

## Notes / Tips
* exeperienced a cordova build error (even though no code or packages changed)
    - you can always delete .meteor/local/cordova
    - then remove the ios platform and add it back
        + meteor remove-platform ios
        + meteor add-platform ios
    - https://forums.meteor.com/t/cordova-error-after-meteor-1-6-upgrade/40536/6

I think the whole local directory can be deleted if needed.

 
