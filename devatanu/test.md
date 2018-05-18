# Node/Express Test

### Question 1

What is `module.exports` and why do we use it?

```text
It is a way to build your own modules that contain resuseable functionality
```

### Question 2

Write one Express route for each of the four CRUD actions.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express")
var app = express()

app.get('/resource/:id', (req,res) => {
    var resource_obj = getResource(req.params["id"]);
    res.json(resource_obj);
});

app.post('/resource', (res,req) => {
    addResource(req.query.resource_name);
});

app.update('/resource/:id', (res,req) => {
    updateResource(req.params["id"], req.query.resource_value)
});

app.delete('/resource/:id', (res,req) => {
    deleteResrouce(req.params["id"]
});
```

### Question 3

Describe the differences between Express and Rails as backend frameworks.

```text
Express is a minimal framework that allows for routing and server. All additional functionalities are added based on npm modules. There are no conventions to follow and the developer is free to choose their own.

Rails is a fully-featured framework that requires the developer for follow convention. However in following convention, development of backend is quicker and provided other developers are familiar with convention then understanding the code is also easier
```

### Question 4

What do the following lines of code do?

```js
var bodyParser = require("body-parser")
app.use(bodyParser.json())
app.use(bodyParser.urlencoded({extended: true}))
```

```text
The code provides middleware for the backend server. The first middleware converts response body to json object. The second middleware allows for objects to be encoded into the url.
```

### Question 5

For this exercise you will be creating an es6 BankAccount class.

It will have the following properties...
* `type` (e.g., "checking"), which should be determined by some input
* `balance`, which should start out as `0`

It should have the following methods...
* `withdraw`, which should decrease the balance by some input
* `deposit`, which should increase the balance by some input
* `showBalance`, which should print the balance in the bank to the console.

The `BankAccount` class has a `transactionHistory` property which keeps track of the withdrawals and deposits made to the account.
* Make sure to indicate whether the transaction increased or decreased the amount of money in the bank.

```js

class BankAccount {
    constructor(type,balanc=0) {
        this.type = type;
        this.balance = balance;
    }


    withdraw(ammount){
        this.balance -= ammount>this.balance ? 0 : ammount;
    }

    deposit(ammount){
        this.balance += ammount;
    }

    showBalance() {
        console.log(this.balance);
    }

}

```


Create an instance of the BankAccount class

```js
var DTsBankAccount = BankAccount('savings',1000000.01);
```
