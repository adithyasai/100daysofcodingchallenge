#### Assessment:

##### Step 1: Define the Contact Class
```javascript
class Contact {
    constructor(name, email, phone) {
        this.name = name;
        this.email = email;
        this.phone = phone;
    }

    displayContact() {
        console.log(`Name: ${this.name}, Email: ${this.email}, Phone: ${this.phone}`);
    }
}
```

##### Step 2: Create a Contacts Array and Functions
```javascript
let contacts = [];

function addContact(name, email, phone) {
    const newContact = new Contact(name, email, phone);
    contacts.push(newContact);
}

function viewContacts() {
    contacts.forEach(contact => {
        contact.displayContact();
    });
}

function searchContacts(name) {
    const foundContact = contacts.find(contact => contact.name.toLowerCase() === name.toLowerCase());
    if (foundContact) {
        foundContact.displayContact();
    } else {
        console.log('Contact not found.');
    }
}
```

##### Step 3: Test Your Contact Management System
```javascript
// Adding Contacts
addContact('Alice Johnson', 'alice.johnson@example.com', '123-456-7890');
addContact('Bob Smith', 'bob.smith@example.com', '098-765-4321');

// Viewing Contacts
console.log('Viewing all contacts:');
viewContacts();

// Searching for a Contact
console.log('Searching for Bob:');
searchContacts('Bob Smith');
```
