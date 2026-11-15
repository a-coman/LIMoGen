# Generation 1
```
!new Bank('bank1')
!bank1.country := 'USA'
!bank1.name := 'Bank of America'
!bank1.bic := 'BOFAUS3N'

!new Bank('bank2')
!bank2.country := 'Germany'
!bank2.name := 'Deutsche Bank'
!bank2.bic := 'DEUTDEFF'

!new Bank('bank3')
!bank3.country := 'UK'
!bank3.name := 'HSBC'
!bank3.bic := 'HBUKGB4B'

!new Account('account1')
!account1.iban := 'US23456789'
!account1.balance := 1200

!new Account('account2')
!account2.iban := 'DE98765432'
!account2.balance := 2500

!new Account('account3')
!account3.iban := 'GB12345678'
!account3.balance := 300

!new Account('account4')
!account4.iban := 'US11223344'
!account4.balance := 4500

!new Account('account5')
!account5.iban := 'DE55667788'
!account5.balance := 0

!new Person('person1')
!person1.firstName := 'John'
!person1.lastName := 'Doe'
!person1.age := 30

!new Person('person2')
!person2.firstName := 'Mary'
!person2.lastName := 'Smith'
!person2.age := 25

!new Person('person3')
!person3.firstName := 'Emma'
!person3.lastName := 'Brown'
!person3.age := 40

!new Person('person4')
!person4.firstName := 'Liam'
!person4.lastName := 'Jones'
!person4.age := 29

!new Person('person5')
!person5.firstName := 'Olivia'
!person5.lastName := 'Johnson'
!person5.age := 19

!new Person('person6')
!person6.firstName := 'Noah'
!person6.lastName := 'Williams'
!person6.age := 35

!insert (person1, account1) into Ownership
!insert (person1, account2) into Ownership
!insert (person1, account3) into Ownership

!insert (person2, account2) into Ownership
!insert (person2, account4) into Ownership

!insert (person3, account5) into Ownership
!insert (person3, account1) into Ownership

!insert (person4, account3) into Ownership
!insert (person4, account5) into Ownership

!insert (person5, account4) into Ownership

!insert (person6, account4) into Ownership

!insert (person1, account3) into Use
!insert (person2, account1) into Use
!insert (person3, account5) into Use
!insert (person4, account2) into Use
!insert (person5, account1) into Use
!insert (person6, account2) into Use

!insert (bank1, account1) into AccountOfBanks
!insert (bank1, account2) into AccountOfBanks
!insert (bank2, account3) into AccountOfBanks
!insert (bank3, account4) into AccountOfBanks
!insert (bank2, account5) into AccountOfBanks

!new Account('account6')
!account6.iban := 'GB24681012'
!account6.balance := 5555

!new Account('account7')
!account7.iban := 'US99887766'
!account7.balance := 789

!new Account('account8')
!account8.iban := 'DE12349876'
!account8.balance := 3400

!insert (person6, account7) into Use
!insert (person1, account8) into Use
!insert (person2, account6) into Ownership

!insert (bank1, account6) into AccountOfBanks
!insert (bank3, account7) into AccountOfBanks
!insert (bank3, account8) into AccountOfBanks

!insert (person3, account8) into Ownership

!new Bank('bank4')
!bank4.country := 'Canada'
!bank4.name := 'Royal Bank of Canada'
!bank4.bic := 'ROYCANC3'

!new Bank('bank5')
!bank5.country := 'France'
!bank5.name := 'BNP Paribas'
!bank5.bic := 'BNPAFRPP'

!new Bank('bank6')
!bank6.country := 'Japan'
!bank6.name := 'Mitsubishi UFJ Financial Group'
!bank6.bic := 'BOTKJPJT'

!new Account('account9')
!account9.iban := 'CA13579111'
!account9.balance := 2100

!new Account('account10')
!account10.iban := 'FR11109876'
!account10.balance := 8700

!new Account('account11')
!account11.iban := 'JP11223344'
!account11.balance := 4300

!new Account('account12')
!account12.iban := 'CA56789012'
!account12.balance := 3200

!new Account('account13')
!account13.iban := 'FR33445566'
!account13.balance := 150

!new Account('account14')
!account14.iban := 'JP55443322'
!account14.balance := 9500

!new Account('account15')
!account15.iban := 'CA66554433'
!account15.balance := 1250

!new Person('person7')
!person7.firstName := 'Sophia'
!person7.lastName := 'Miller'
!person7.age := 27

!new Person('person8')
!person8.firstName := 'Mason'
!person8.lastName := 'Davis'
!person8.age := 31

!new Person('person9')
!person9.firstName := 'Isabella'
!person9.lastName := 'Garcia'
!person9.age := 45

!new Person('person10')
!person10.firstName := 'James'
!person10.lastName := 'Martinez'
!person10.age := 60

!new Person('person11')
!person11.firstName := 'Mia'
!person11.lastName := 'Rodriguez'
!person11.age := 40

!new Person('person12')
!person12.firstName := 'Ethan'
!person12.lastName := 'Martinez'
!person12.age := 50

!insert (person7, account9) into Ownership
!insert (person8, account10) into Ownership
!insert (person8, account12) into Ownership

!insert (person9, account11) into Ownership
!insert (person9, account13) into Ownership

!insert (person10, account12) into Ownership
!insert (person10, account14) into Ownership

!insert (person11, account15) into Ownership
!insert (person11, account9) into Ownership

!insert (person12, account14) into Ownership
!insert (person12, account13) into Ownership

!insert (person7, account11) into Use
!insert (person8, account9) into Use
!insert (person9, account10) into Use
!insert (person10, account15) into Use
!insert (person11, account11) into Use
!insert (person12, account12) into Use

!insert (bank4, account9) into AccountOfBanks
!insert (bank5, account10) into AccountOfBanks
!insert (bank6, account11) into AccountOfBanks
!insert (bank4, account12) into AccountOfBanks
!insert (bank5, account13) into AccountOfBanks
!insert (bank6, account14) into AccountOfBanks
!insert (bank4, account15) into AccountOfBanks

!new Bank('bank7')
!bank7.country := 'Australia'
!bank7.name := 'Commonwealth Bank'
!bank7.bic := 'CTBAAU2S'

!new Bank('bank8')
!bank8.country := 'India'
!bank8.name := 'State Bank of India'
!bank8.bic := 'SBININBB'

!new Bank('bank9')
!bank9.country := 'Italy'
!bank9.name := 'UniCredit'
!bank9.bic := 'UNCRITMM'

!new Account('account16')
!account16.iban := 'AU10293847'
!account16.balance := 5300

!new Account('account17')
!account17.iban := 'IN29384756'
!account17.balance := 6300

!new Account('account18')
!account18.iban := 'IT38475629'
!account18.balance := 4100

!new Account('account19')
!account19.iban := 'AU12345678'
!account19.balance := 3300

!new Account('account20')
!account20.iban := 'IN87654321'
!account20.balance := 2100

!new Account('account21')
!account21.iban := 'IT11223344'
!account21.balance := 8900

!new Account('account22')
!account22.iban := 'AU99887766'
!account22.balance := 2600

!new Person('person13')
!person13.firstName := 'Ava'
!person13.lastName := 'Harris'
!person13.age := 28

!new Person('person14')
!person14.firstName := 'Michael'
!person14.lastName := 'Clark'
!person14.age := 34

!new Person('person15')
!person15.firstName := 'Emily'
!person15.lastName := 'Lewis'
!person15.age := 22

!new Person('person16')
!person16.firstName := 'Alexander'
!person16.lastName := 'Young'
!person16.age := 37

!insert (person13, account16) into Ownership
!insert (person14, account17) into Ownership

!insert (person15, account17) into Ownership
!insert (person15, account18) into Ownership

!insert (person16, account19) into Ownership
!insert (person16, account20) into Ownership

!insert (person13, account21) into Ownership
!insert (person14, account20) into Ownership

!insert (person14, account22) into Ownership
!insert (person15, account19) into Ownership

!insert (person16, account22) into Use
!insert (person13, account18) into Use
!insert (person14, account16) into Use
!insert (person15, account21) into Use

!insert (bank7, account16) into AccountOfBanks
!insert (bank8, account17) into AccountOfBanks
!insert (bank9, account18) into AccountOfBanks
!insert (bank7, account19) into AccountOfBanks
!insert (bank8, account20) into AccountOfBanks
!insert (bank9, account21) into AccountOfBanks
!insert (bank9, account22) into AccountOfBanks

```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 240 | 0.00% |
| Multiplicities Errors | 2 | 74 | 2.70% |
| Invariants Errors | 0 | 2 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `Ownership':
  Object `account7' of class `Account' is connected to 0 objects of class `Person'
  at association end `owner' but the multiplicity is specified as `1..2'.
```
```
Multiplicity constraint violation in association `Ownership':
  Object `account4' of class `Account' is connected to 3 objects of class `Person'
  at association end `owner' but the multiplicity is specified as `1..2'.
```

| Bank | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| IBANs | 22 | 22 | 100.00% |
| BICs | 0 | 9 | 0.00% |
| Countries | 1 | 9 | 11.11% |

| Failed IBANs | 
|---| 
```
US23456789
```
```
DE98765432
```
```
GB12345678
```
```
US11223344
```
```
DE55667788
```
```
GB24681012
```
```
US99887766
```
```
DE12349876
```
```
CA13579111
```
```
FR11109876
```
```
JP11223344
```
```
CA56789012
```
```
FR33445566
```
```
JP55443322
```
```
CA66554433
```
```
AU10293847
```
```
IN29384756
```
```
IT38475629
```
```
AU12345678
```
```
IN87654321
```
```
IT11223344
```
```
AU99887766
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
| Syntax Errors | 0 | 240 | 0.00% |
| Multiplicities Errors | 2 | 74 | 2.70% |
| Invariants Errors | 0 | 2 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `Ownership':
  Object `account7' of class `Account' is connected to 0 objects of class `Person'
  at association end `owner' but the multiplicity is specified as `1..2'.
```
```
Multiplicity constraint violation in association `Ownership':
  Object `account4' of class `Account' is connected to 3 objects of class `Person'
  at association end `owner' but the multiplicity is specified as `1..2'.
```

| Bank | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| IBANs | 22 | 22 | 100.00% |
| BICs | 0 | 9 | 0.00% |
| Countries | 1 | 9 | 11.11% |

| Failed IBANs | 
|---| 
```
US23456789
```
```
DE98765432
```
```
GB12345678
```
```
US11223344
```
```
DE55667788
```
```
GB24681012
```
```
US99887766
```
```
DE12349876
```
```
CA13579111
```
```
FR11109876
```
```
JP11223344
```
```
CA56789012
```
```
FR33445566
```
```
JP55443322
```
```
CA66554433
```
```
AU10293847
```
```
IN29384756
```
```
IT38475629
```
```
AU12345678
```
```
IN87654321
```
```
IT11223344
```
```
AU99887766
```

| Failed Countries | 
|---| 
```
UK
```

