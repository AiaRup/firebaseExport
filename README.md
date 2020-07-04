# firebaseExport

You can use this small project to export a json file with data to Firebase Cloud Firestore collection.

To get started: 

## Install

```bash
# with npm
npm install

# or with Yarn
yarn install
```

## Usage

### Firesote setup

First you need to create a project at [Firebase](https://firebase.google.com/).
Then you need to get yout project credentials, it will look something like this:


```bash
{
  apiKey: "API_KEY_HERE",
  authDomain: "AUTH_DOMAIN_HERE",
  databaseURL: "DATABASE_URL_HERE",
  projectId: "PROJECT_ID_HERE",
  storageBucket: "STORAGE_BUCKET_HERE",
  messagingSenderId: "MESSAGING_ID_HERE"
}
```

Create an `.env` file with all this variables. It will look something like that (replace `...` with you actual values:

```bash
{
API_KEY=...
AUTH_DOMAIN=...
DATABASE_URL=...
PROJECT_ID=...
STORAGE_BUCKET=...
MEASUREMENT_ID=...
}
```

### Firebase service account

After creating yout project, you can go to `Settings => Users and Permissions => Service Accounts => Generate New Private Key`.
This action will download a JSON file to your computer. Rename it to `serviceAccount.json` and put it in the root folder of the project.

### Export data

Change the file of `listings.json` to the file you would like to export.
Your JSON file must have a key with the name of the collection, like `{ "COLLECTION_NAME" : [...YOUR_ARRAY_OF_DATA]}` when loading the file.
You can look at the `listings.json` file and see that the key root is "listings".
Don't forget to change it here as well (export.js file):

```javascript
await firestoreService.restore('./YOUR_FILE_NAME.json');
```

 Execute this command to export your data to your firestore:
 
 ```javascript
node export.js
```

Done 🌈
