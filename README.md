# BankJS_clean

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
