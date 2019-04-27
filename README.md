# MVP:

https://projects.invisionapp.com/share/2NR7PCDE7HQ

## user can log into their account

some combination of the following:
- https://docs.mongodb.com/stitch/authentication/userpass/
- https://docs.mongodb.com/stitch-sdks/js-react-native/4/index.html

Example Snippet

Try the following code in a script that you are bundling to a frontend JavaScript application.

```Javascript
const {
    Stitch,
    RemoteMongoClient,
    AnonymousCredential
} = require('mongodb-stitch-browser-sdk');

const client = Stitch.initializeDefaultAppClient('slumsapp-qbxrr');

const db = client.getServiceClient(RemoteMongoClient.factory, 'slumsapp-qbxrr').db('SlumTests');

client.auth.loginWithCredential(new AnonymousCredential()).then(user =>
  db.collection('SlumTest').updateOne({owner_id: client.auth.user.id}, {$set:{number:42}}, {upsert:true})
).then(() =>
  db.collection('SlumTest').find({owner_id: client.auth.user.id}, { limit: 100}).asArray()
).then(docs => {
    console.log("Found docs", docs)
    console.log("[MongoDB Stitch] Connected to Stitch")
}).catch(err => {
    console.error(err)
});
```

## user can take SLUMS diagnostic test

## test is sent to remote database as one document within cloud db collection 

### libraries

https://www.npmjs.com/package/react-native-material-ui
https://docs.mongodb.com/stitch-sdks/js-react-native/4/index.html

# Phase Two

## audio questions

## image questions

# Phase Three

## persistent login

## fingerprint authentication

## doctor/family member portal 

## push notifications


