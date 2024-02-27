### Assignment1: Library System
```javascript
function Book(title, author, pages, read) {
    this.title = title;
    this.author = author;
    this.pages = pages;
    this.read = read;
    this.info = function() {
      return `${this.title} by ${this.author}, ${this.pages} pages, ${this.read ? 'read' : 'not read yet'}`;
    };
  }
  
  let Library = {
    books: [],
    addBook(book) {
      this.books.push(book);
    },
    listBooks() {
      this.books.forEach(book => console.log(book.info()));
    }
  };
  
  let book1 = new Book('The Hobbit', 'J.R.R. Tolkien', 295, false);
  Library.addBook(book1);
  Library.listBooks();
  ```

  ### Assignment2: Simple Bank System
  ```javascript
  function BankAccount(accountNumber) {
    this.accountNumber = accountNumber;
    let balance = 0;
  
    this.deposit = function(amount) {
      balance += amount;
      console.log(`Deposited ${amount}. Current balance: ${balance}`);
    };
  
    this.withdraw = function(amount) {
      if (amount <= balance) {
        balance -= amount;
        console.log(`Withdrew ${amount}. Current balance: ${balance}`);
      } else {
        console.log('Insufficient funds.');
      }
    };
  
    this.getBalance = function() {
      return balance;
    };
  }
  
  function SavingsAccount(accountNumber, interestRate) {
    BankAccount.call(this, accountNumber);
    this.interestRate = interestRate;
  
    let parentWithdraw = this.withdraw;
    this.withdraw = function(amount) {
      if (amount > 500) {
        console.log('Withdrawal limit reached');
      } else {
        parentWithdraw(amount);
      }
    };
  }
  
  let mySavings = new SavingsAccount('12345', 0.02);
  mySavings.deposit(1000);
  mySavings.withdraw(600); // Should show a limit message
  mySavings.withdraw(200); // Should proceed with withdrawal
  ```