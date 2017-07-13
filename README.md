# React Contacts Book App

### About
This App manages a contact list, in which the user can add and delete contacts as well as search through them. It is built with React, and uses a small node/express backend server. 

### To run this App

Setup the server
* Clone the project with `git clone https://github.com/tomroper/react-contacts-server.git`
* Install dependencies with `npm install`
* Start the sever with `node server.js` , this is then accessible on port 5001

For the App
* Clone the repo with `git clone https://github.com/tomroper/react-contacts-app.git`
* Install dependencies with `npm install`
* The app can be started with `yarn start` or `npm start` , and will run on port 3000

### Development
This App is currently in active development

We start with the initial state set with 3 contacts.

When we click to delete a contact, the contact is passed into this function and setState runs a `filter()`  

```
removeContact = (contact) => {
    this.setState((state) => ({
      contacts: state.contacts.filter((c) => c.id !== contact.id )
    }))
  }
 ```

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).
