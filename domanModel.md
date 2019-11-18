| Objects       | Methods               | Behaviours                                           |
| ------------- | --------------------- | ---------------------------------------------------- |
| _Account_     | \_balance             | => integer                                           |
|               | \_transactions        | => Array of transactions                             |
|               | deposit(amount :int)  | => changes balance by +amount,                       |
|               |                       | => pushes a "credit" transaction to transactions     |
|               |                       | => returns transaction object                        |
|               | withdraw(amount :int) | => changes balance by -amount,                       |
|               |                       | => pushes a "debit" transaction to transactions      |
|               |                       | => raises an error if balance - amount < 0           |
|               |                       | => returns transaction object                        |
|               | statement()           | => calls show on an instance of this.StatementClass  |
| _Transaction_ | processedAt           | => Date object, reflects moment transaction was made |
|               | type                  | => "credit" or "debit"                               |
|               | amount                | => integer                                           |
|               | balanceAfter          | => integer                                           |
| _Statement_   | show()                | => output a statement of all transactions to stdout  |
|               | \_transactions        | => transactions for which the statement is created   |
