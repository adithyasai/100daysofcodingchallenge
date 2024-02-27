### Assignment: Personal Finance Tracker

```javascript
const financeTracker = () => {
  let income = 0;
  let expenses = 0;

  const addIncome = (amount) => income += amount;
  const addExpense = (amount) => expenses += amount;
  const getBalance = () => income - expenses;

  return {
    addIncome,
    addExpense,
    getBalance
  };
};

const myFinances = financeTracker();
myFinances.addIncome(1000);
myFinances.addExpense(300);
myFinances.addExpense(50);
console.log(`Current Balance: $${myFinances.getBalance()}`); // Output: Current Balance: $650
```
