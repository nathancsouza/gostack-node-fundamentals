# bootcamp-gostack-challenge

## 🚀 About the challenge


In this challenge, you must create an application to continue training what you have learned so far in Node.js with TypeScript, using the concept of models, repositories and services!

This will be an application for storing incoming and outcome financial transactions, which should allow the registration and listing of these transactions.


## Application routes
<ul><li>
POST / transactions: The route must receive title, value and type within the body of the request, type is the type of the transaction, which must be income for entries (deposits) and outcome for exits (withdrawals). When registering a new transaction, it must be stored inside an object with the format like the following:</li></ul>

```
{
  "id": "uuid",
  "title": "Salary",
  "value": 3000,
  "type": "income"
}
```
<ul><li>
GET / transactions: This route should return a listing with all the transactions you have registered so far, together with the sum of the entries, withdrawals and total credit. This route must return an object with the following format:
</li></ul>

```
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salary",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Invoice payment",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Gamer Chair",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

## Testing specification

For this challenge we have the following tests:
<ul><li>
should be able to create a new transaction: For this test to pass, your application must allow a transaction to be created, and return a json with the created transaction.</li>
<li>
should be able to list the transactions: In order for this test to pass, your application must allow an object containing all transactions to be returned together with the balance of income, outcome and total transactions that have been created so far.</li>
<li>
should not be able to create outcome transaction without a valid balance: In order for this test to pass, your application must not allow an outcome type transaction to exceed the total amount the user has in the box, returning a response with HTTP 400 code and one error message in the following format: {error: string}
<ul></li>
