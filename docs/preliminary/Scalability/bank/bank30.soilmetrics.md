# Generation 1
```
-- Creating 5 Bank instances
!new Bank('Bank1')
!Bank1.country := 'USA'
!Bank1.name := 'Global Bank'
!Bank1.bic := 'GBUS1'

!new Bank('Bank2')
!Bank2.country := 'Germany'
!Bank2.name := 'Deutsche Bank'
!Bank2.bic := 'DEUT2'

!new Bank('Bank3')
!Bank3.country := 'Japan'
!Bank3.name := 'Tokyo Bank'
!Bank3.bic := 'TOKJP3'

!new Bank('Bank4')
!Bank4.country := 'UK'
!Bank4.name := 'London Bank'
!Bank4.bic := 'LONUK4'

!new Bank('Bank5')
!Bank5.country := 'Australia'
!Bank5.name := 'Sydney Bank'
!Bank5.bic := 'SYDAU5'

-- Creating 15 Account instances
!new Account('Account1')
!Account1.iban := 'US001'
!Account1.balance := 1000

!new Account('Account2')
!Account2.iban := 'DE002'
!Account2.balance := 2000

!new Account('Account3')
!Account3.iban := 'JP003'
!Account3.balance := 1500

!new Account('Account4')
!Account4.iban := 'UK004'
!Account4.balance := 2500

!new Account('Account5')
!Account5.iban := 'AU005'
!Account5.balance := 3000

!new Account('Account6')
!Account6.iban := 'US006'
!Account6.balance := 0 -- Corner case: zero balance (valid)

!new Account('Account7')
!Account7.iban := 'DE007'
!Account7.balance := 1800

!new Account('Account8')
!Account8.iban := 'JP008'
!Account8.balance := 2200

!new Account('Account9')
!Account9.iban := 'UK009'
!Account9.balance := 2700

!new Account('Account10')
!Account10.iban := 'AU010'
!Account10.balance := 3500

!new Account('Account11')
!Account11.iban := 'US011'
!Account11.balance := 4000

!new Account('Account12')
!Account12.iban := 'DE012'
!Account12.balance := 0 -- Another corner case: zero balance (valid)

!new Account('Account13')
!Account13.iban := 'JP013'
!Account13.balance := 3100

!new Account('Account14')
!Account14.iban := 'UK014'
!Account14.balance := 4100

!new Account('Account15')
!Account15.iban := 'AU015'
!Account15.balance := 5000

-- Creating 10 Person instances
!new Person('Person1')
!Person1.firstName := 'John'
!Person1.lastName := 'Doe'
!Person1.age := 28

!new Person('Person2')
!Person2.firstName := 'Jane'
!Person2.lastName := 'Smith'
!Person2.age := 34

!new Person('Person3')
!Person3.firstName := 'Michael'
!Person3.lastName := 'Johnson'
!Person3.age := 45

!new Person('Person4')
!Person4.firstName := 'Emily'
!Person4.lastName := 'Davis'
!Person4.age := 22

!new Person('Person5')
!Person5.firstName := 'David'
!Person5.lastName := 'Wilson'
!Person5.age := 19

!new Person('Person6')
!Person6.firstName := 'Linda'
!Person6.lastName := 'Martinez'
!Person6.age := 30

!new Person('Person7')
!Person7.firstName := 'James'
!Person7.lastName := 'Brown'
!Person7.age := 38

!new Person('Person8')
!Person8.firstName := 'Patricia'
!Person8.lastName := 'Taylor'
!Person8.age := 47

!new Person('Person9')
!Person9.firstName := 'Robert'
!Person9.lastName := 'Anderson'
!Person9.age := 53

!new Person('Person10')
!Person10.firstName := 'Linda'
!Person10.lastName := 'Thomas'
!Person10.age := 60

-- Associations
!insert (Person1, Account1) into Ownership
!insert (Person2, Account2) into Ownership
!insert (Person3, Account3) into Ownership
!insert (Person1, Account4) into Ownership
!insert (Person4, Account5) into Ownership
!insert (Person5, Account5) into Ownership
!insert (Person6, Account6) into Ownership
!insert (Person7, Account7) into Ownership
!insert (Person6, Account8) into Ownership
!insert (Person8, Account9) into Ownership
!insert (Person9, Account10) into Ownership
!insert (Person10, Account11) into Ownership
!insert (Person8, Account12) into Ownership
!insert (Person9, Account13) into Ownership
!insert (Person10, Account14) into Ownership
!insert (Person7, Account15) into Ownership

!insert (Person1, Account1) into Use
!insert (Person2, Account2) into Use
!insert (Person3, Account3) into Use
!insert (Person4, Account4) into Use
!insert (Person5, Account5) into Use
!insert (Person6, Account6) into Use
!insert (Person7, Account7) into Use
!insert (Person8, Account8) into Use
!insert (Person9, Account9) into Use
!insert (Person10, Account10) into Use

!insert (Bank1, Account1) into AccountOfBanks
!insert (Bank2, Account2) into AccountOfBanks
!insert (Bank3, Account3) into AccountOfBanks
!insert (Bank4, Account4) into AccountOfBanks
!insert (Bank5, Account5) into AccountOfBanks
!insert (Bank1, Account6) into AccountOfBanks
!insert (Bank2, Account7) into AccountOfBanks
!insert (Bank3, Account8) into AccountOfBanks
!insert (Bank4, Account9) into AccountOfBanks
!insert (Bank5, Account10) into AccountOfBanks
!insert (Bank1, Account11) into AccountOfBanks
!insert (Bank2, Account12) into AccountOfBanks
!insert (Bank3, Account13) into AccountOfBanks
!insert (Bank4, Account14) into AccountOfBanks
!insert (Bank5, Account15) into AccountOfBanks

-- Done creating 30 entities
```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 146 | 0.00% |
| Multiplicities Errors | 0 | 41 | 0.00% |
| Invariants Errors | 0 | 2 | 0.00% |

| Bank | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| IBANs | 15 | 15 | 100.00% |
| BICs | 5 | 5 | 100.00% |
| Countries | 1 | 5 | 20.00% |

| Failed IBANs | 
|---| 
```
US001
```
```
DE002
```
```
JP003
```
```
UK004
```
```
AU005
```
```
US006
```
```
DE007
```
```
JP008
```
```
UK009
```
```
AU010
```
```
US011
```
```
DE012
```
```
JP013
```
```
UK014
```
```
AU015
```

| Failed BICs | 
|---| 
```
GBUS1
```
```
DEUT2
```
```
TOKJP3
```
```
LONUK4
```
```
SYDAU5
```

| Failed Countries | 
|---| 
```
UK
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | bank | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 146 | 0.00% |
| Multiplicities Errors | 0 | 41 | 0.00% |
| Invariants Errors | 0 | 2 | 0.00% |

| Bank | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| IBANs | 15 | 15 | 100.00% |
| BICs | 5 | 5 | 100.00% |
| Countries | 1 | 5 | 20.00% |

| Failed IBANs | 
|---| 
```
US001
```
```
DE002
```
```
JP003
```
```
UK004
```
```
AU005
```
```
US006
```
```
DE007
```
```
JP008
```
```
UK009
```
```
AU010
```
```
US011
```
```
DE012
```
```
JP013
```
```
UK014
```
```
AU015
```

| Failed BICs | 
|---| 
```
GBUS1
```
```
DEUT2
```
```
TOKJP3
```
```
LONUK4
```
```
SYDAU5
```

| Failed Countries | 
|---| 
```
UK
```

