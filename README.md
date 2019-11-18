# BankJS_clean
#### *tech test*
### Acceptance criteria

**Given** a client makes a deposit of 1000 on 10-01-2012  
**And** a deposit of 2000 on 13-01-2012  
**And** a withdrawal of 500 on 14-01-2012  
**When** she prints her bank statement  
**Then** she would see

```
date || credit || debit || balance
14/01/2012 || || 500.00 || 2500.00
13/01/2012 || 2000.00 || || 3000.00
10/01/2012 || 1000.00 || || 1000.00
```

## Domain Model

| Objects       | Methods                | Behaviours                                           |
| ------------- | ---------------------- | ---------------------------------------------------- |
| _Account_     | \_balance(public)      | => integer                                           |
|               | \_transactions(public) | => Array of transactions                             |
|               | deposit(amount :int)   | => changes balance by +amount,                       |
|               |                        | => pushes + transaction to transactions              |
|               |                        | => returns transaction object                        |
|               | withdraw(amount :int)  | => changes balance by -amount,                       |
|               |                        | => pushes a - transaction to transactions            |
|               |                        | => raises an error if balance - amount < 0           |
|               |                        | => returns transaction object                        |
|               | statement()            | => calls show on an instance of this.StatementClass  |
| _Transaction_ | processedAt            | => Date object, reflects moment transaction was made |
|               | type                   | => "credit" or "debit"                               |
|               | amount                 | => integer                                           |
|               | balanceAfter           | => integer                                           |
| _Statement_   | show()                 | => output a statement of all transactions to stdout  |
|               | \_transactions(public) | => transactions for which the statement is created   |
