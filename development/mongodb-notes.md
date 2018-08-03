# Various notes on mongodb

https://docs.mongodb.com/ecosystem/drivers/driver-compatibility-reference/#node-js-driver-compatibility

#### Related
* https://medium.freecodecamp.org/introduction-to-mongoose-for-mongodb-d2a7aa593c57
* https://forums.meteor.com/t/mongoose-in-meteor/28269


## Useful mongodb commands
* db.getCollectionNames();
* db.collection.getIndexes();

## Meteor
* to tell Meteor's version of mongodb, run `meteor mongo`
* to tell Meteor's mongo node driver, from meteor shell run: `MongoInternals.NpmModules.mongodb.version`
    - described here: https://github.com/meteor/meteor/tree/devel/packages/mongo
* meteor's node version: meteor node --version
* meteor's npm version: meteor npm --version

## Compose
* to tell version of database
    - connect using mongo shell (usually lists version when connecting)
    - from shell prompt, run command `db.serverStatus();`
    - from Compose, go to deployment > Monitoring > Status tab, then scroll down
