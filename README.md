# React Contacts Book App
#### In active development

![Contacts App](http://i.imgur.com/kpR9Zwc.png)

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

### Functionality
We start with the initial state set with 3 contacts.

#### Searching Contacts

In our search `<input>`, `value` is set by the component state, a `onChange` is used to run the `updateQuery()`, that mutates the component state and therefore updates the value. This is a nice way for us let React handle the state and UI updating

```
    <input
      value={this.state.query}
      onChange={(event) => this.updateQuery(event.target.value)}
    />
```

As we know, when the state changes, the components `render()` is called, and the UI updates. An if/else lets us check whether we have anything in the query state, and if so to `let showingContacts` be the array we are given after running a `.test()` function on `this.props.contacts`

```
    let showingContacts
    if (this.state.query) {
      const match = new RegExp(escapeRegExp(this.state.query), 'i')
      showingContacts = this.props.contacts.filter((contact) => match.test(contact.name))
    } else {
      showingContacts = this.props.contacts
    }
    showingContacts.sort(sortBy('name'))
```

#### Deleting Contacts

When we click to delete a contact, the contact is passed into this function and setState runs a `filter()`  

```
removeContact = (contact) => {
    this.setState((state) => ({
      contacts: state.contacts.filter((c) => c.id !== contact.id )
    }))
  }
 ```

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).
