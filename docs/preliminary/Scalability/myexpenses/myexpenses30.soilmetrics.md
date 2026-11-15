# Generation 1
```
!new Expense('expense1')
!expense1.amount := 1000.0
!expense1.startDate := Date('2023-01-01')
!expense1.endDate := Date('2023-12-31')

!new Expense('expense2')
!expense2.amount := 1500.0
!expense2.startDate := Date('2023-02-01')
!expense2.endDate := Date('2023-12-31')

!new Bill('bill1')
!bill1.amount := 500.0
!bill1.category := 'Utilities'
!bill1.date := Date('2023-01-10')
!bill1.paymentMethod := #CREDIT_CARD
!bill1.status := #VERIFIED
!insert ('expense1', 'bill1') into ExpenseContainsBills

!new Bill('bill2')
!bill2.amount := 300.0
!bill2.category := 'Groceries'
!bill2.date := Date('2023-01-15')
!bill2.paymentMethod := #CASH
!bill2.status := #PENDING
!insert ('expense1', 'bill2') into ExpenseContainsBills

!new Bill('bill3')
!bill3.amount := 700.0
!bill3.category := 'Rent'
!bill3.date := Date('2023-02-05')
!bill3.paymentMethod := #CHECK
!bill3.status := #VALIDATED
!insert ('expense2', 'bill3') into ExpenseContainsBills

!new Bill('bill4')
!bill4.amount := 800.0
!bill4.category := 'Entertainment'
!bill4.date := Date('2023-02-20')
!bill4.paymentMethod := #CREDIT_CARD
!bill4.status := #REFUSED
!insert ('expense2', 'bill4') into ExpenseContainsBills

!new Comment('comment1')
!comment1.text := 'Monthly utility bill.'
!insert ('expense1', 'comment1') into ExpenseComment

!new Comment('comment2')
!comment2.text := 'Weekly grocery shopping.'
!insert ('expense1', 'comment2') into ExpenseComment

!new Comment('comment3')
!comment3.text := 'February rent payment.'
!insert ('expense2', 'comment3') into ExpenseComment

!new Currency('currency1')
!currency1.name := 'US Dollar'
!currency1.abbreviation := 'USD'
!insert ('bill1', 'currency1') into BillCurrency
!insert ('bill2', 'currency1') into BillCurrency
!insert ('bill3', 'currency1') into BillCurrency
!insert ('bill4', 'currency1') into BillCurrency

!new Expense('expense3')
!expense3.amount := 200.0
!expense3.startDate := Date('2023-03-05')
!expense3.endDate := Date('2023-03-15')

!new Bill('bill5')
!bill5.amount := 200.0
!bill5.category := 'Dining'
!bill5.date := Date('2023-03-06')
!bill5.paymentMethod := #CASH
!bill5.status := #REFUNDED
!insert ('expense3', 'bill5') into ExpenseContainsBills
!insert ('bill5', 'currency1') into BillCurrency

!new Comment('comment4')
!comment4.text := 'Dinner with friends.'
!insert ('expense3', 'comment4') into ExpenseComment

!new Expense('expense4')
!expense4.amount := 750.0
!expense4.startDate := Date('2023-03-01')
!expense4.endDate := Date('2023-03-31')

!new Bill('bill6')
!bill6.amount := 750.0
!bill6.category := 'New Phone'
!bill6.date := Date('2023-03-15')
!bill6.paymentMethod := #CREDIT_CARD
!bill6.status := #DRAFT
!insert ('expense4', 'bill6') into ExpenseContainsBills
!insert ('bill6', 'currency1') into BillCurrency

!new Comment('comment5')
!comment5.text := 'Purchased a new phone.'
!insert ('expense4', 'comment5') into ExpenseComment

!new Currency('currency2')
!currency2.name := 'Euro'
!currency2.abbreviation := 'EUR'

!new Expense('expense5')
!expense5.amount := 600.0
!expense5.startDate := Date('2023-03-10')
!expense5.endDate := Date('2023-03-20')

!new Bill('bill7')
!bill7.amount := 600.0
!bill7.category := 'Travel'
!bill7.date := Date('2023-03-12')
!bill7.paymentMethod := #CREDIT_CARD
!bill7.status := #VALIDATED
!insert ('expense5', 'bill7') into ExpenseContainsBills
!insert ('bill7', 'currency2') into BillCurrency

!new Comment('comment6')
!comment6.text := 'Weekend getaway trip.'
!insert ('expense5', 'comment6') into ExpenseComment

!new Expense('expense6')
!expense6.amount := 250.0
!expense6.startDate := Date('2023-04-01')
!expense6.endDate := Date('2023-04-15')

!new Bill('bill8')
!bill8.amount := 250.0
!bill8.category := 'Health'
!bill8.date := Date('2023-04-02')
!bill8.paymentMethod := #CHECK
!bill8.status := #VERIFIED
!insert ('expense6', 'bill8') into ExpenseContainsBills
!insert ('bill8', 'currency1') into BillCurrency

!new Comment('comment7')
!comment7.text := 'Medical check-up.'
!insert ('expense6', 'comment7') into ExpenseComment

!new Expense('expense7')
!expense7.amount := 900.0
!expense7.startDate := Date('2023-04-10')
!expense7.endDate := Date('2023-04-20')

!new Bill('bill9')
!bill9.amount := 900.0
!bill9.category := 'Home Improvement'
!bill9.date := Date('2023-04-12')
!bill9.paymentMethod := #CREDIT_CARD
!bill9.status := #PENDING
!insert ('expense7', 'bill9') into ExpenseContainsBills
!insert ('bill9', 'currency2') into BillCurrency

!new Comment('comment8')
!comment8.text := 'Paint and renovation.'
!insert ('expense7', 'comment8') into ExpenseComment

!new Expense('expense8')
!expense8.amount := 150.0
!expense8.startDate := Date('2023-04-05')
!expense8.endDate := Date('2023-04-25')

!new Bill('bill10')
!bill10.amount := 150.0
!bill10.category := 'Subscription'
!bill10.date := Date('2023-04-06')
!bill10.paymentMethod := #CASH
!bill10.status := #REFUNDED
!insert ('expense8', 'bill10') into ExpenseContainsBills
!insert ('bill10', 'currency1') into BillCurrency

!new Comment('comment9')
!comment9.text := 'Annual magazine subscription.'
!insert ('expense8', 'comment9') into ExpenseComment
```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 28 | 145 | 19.31% |
| Multiplicities Errors | 31 | 29 | 106.90% |
| Invariants Errors | 1 | 2 | 50.00% |

| Syntax Errors | 
|---| 
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill8'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill9'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense8'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill10'' is of type `String'.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill10' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill9' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill7' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill8' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill5' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill6' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill3' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill4' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill1' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill2' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `currency1' of class `Currency' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `currency2' of class `Currency' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment6' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment5' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment4' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment3' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment2' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment1' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment9' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment8' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment7' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill10' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill9' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill7' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill8' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill5' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill6' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill3' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill4' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill1' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill2' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```

| Invariants Errors | 
|---| 
```
checking invariant (1) `Expense::expenseSumOfBills': FAILED.
```

| MyExpenses | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Dates | 0 | 8 | 0.00% |

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | myexpenses | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 28 | 145 | 19.31% |
| Multiplicities Errors | 31 | 29 | 106.90% |
| Invariants Errors | 1 | 2 | 50.00% |

| Syntax Errors | 
|---| 
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill1'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill2'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense3'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense4'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense5'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill8'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense6'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill9'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseComment' must be of type `Expense', but `'expense7'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `ExpenseContainsBills' must be of type `Expense', but `'expense8'' is of type `String'.
```
```
<input>:1:0: Participant 1 of association `BillCurrency' must be of type `Bill', but `'bill10'' is of type `String'.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill10' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill9' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill7' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill8' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill5' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill6' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill3' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill4' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill1' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `bill2' of class `Bill' is connected to 0 objects of class `Currency'
  at association end `currency' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `currency1' of class `Currency' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `BillCurrency':
  Object `currency2' of class `Currency' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment6' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment5' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment4' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment3' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment2' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment1' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment9' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment8' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseComment':
  Object `comment7' of class `Comment' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill10' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill9' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill7' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill8' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill5' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill6' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill3' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill4' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill1' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ExpenseContainsBills':
  Object `bill2' of class `Bill' is connected to 0 objects of class `Expense'
  at association end `expense' but the multiplicity is specified as `1'.
```

| Invariants Errors | 
|---| 
```
checking invariant (1) `Expense::expenseSumOfBills': FAILED.
```

| MyExpenses | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Dates | 0 | 8 | 0.00% |

