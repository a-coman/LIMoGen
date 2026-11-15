# Generation 1
```
!new AddressBook('addressBook1')

!new Person('person1')
!person1.name := 'Alice'
!person1.phone := '123-456-7890'
!person1.website := 'www.alice.com'
!person1.email := 'alice@example.com'
!person1.title := 'Manager'

!new Person('person2')
!person2.name := 'Bob'
!person2.phone := '234-567-8901'
!person2.website := 'www.bob.com'
!person2.email := 'bob@example.com'
!person2.title := 'Developer'

!new Person('person3')
!person3.name := 'Charlie'
!person3.phone := '345-678-9012'
!person3.website := 'www.charlie.com'
!person3.email := 'charlie@example.com'
!person3.title := 'Consultant'

!new Company('company1')
!company1.name := 'Tech Corp'
!company1.phone := '456-789-0123'
!company1.website := 'www.techcorp.com'
!company1.email := 'contact@techcorp.com'
!company1.industry := 'Technology'

!new Company('company2')
!company2.name := 'Health Inc'
!company2.phone := '567-890-1234'
!company2.website := 'www.healthinc.com'
!company2.email := 'contact@healthinc.com'
!company2.industry := 'Healthcare'

!new Address('address1')
!address1.city := 'New York'
!address1.houseNr := '1'
!address1.street := 'Broadway'

!new Address('address2')
!address2.city := 'San Francisco'
!address2.houseNr := '101'
!address2.street := 'Market Street'

!new Address('address3')
!address3.city := 'Los Angeles'
!address3.houseNr := '200'
!address3.street := 'Sunset Boulevard'

!new Note('note1')
!note1.author := 'Alice'
!note1.time := Date('2023-10-05')
!note1.type := #MEETING
!note1.comment := 'Discuss project updates'

!new Note('note2')
!note2.author := 'Bob'
!note2.time := Date('2023-10-06')
!note2.type := #CALL
!note2.comment := 'Call client regarding requirements'

!new Note('note3')
!note3.author := 'Charlie'
!note3.time := Date('2023-10-07')
!note3.type := #EMAIL
!note3.comment := 'Email team about deliverables'

!new Relationship('relationship1')
!relationship1.type := #BOSS

!new Relationship('relationship2')
!relationship2.type := #COWORKER

!new Relationship('relationship3')
!relationship3.type := #SUBDIVISION

!insert (addressBook1, person1) into AddressBookMadeOfContact
!insert (addressBook1, person2) into AddressBookMadeOfContact
!insert (addressBook1, person3) into AddressBookMadeOfContact
!insert (addressBook1, company1) into AddressBookMadeOfContact
!insert (addressBook1, company2) into AddressBookMadeOfContact

!insert (person1, note1) into ContactContainsNote
!insert (person2, note2) into ContactContainsNote
!insert (person3, note3) into ContactContainsNote

!insert (person1, relationship1) into ContactToRelationship
!insert (person2, relationship2) into ContactToRelationship
!insert (company1, relationship3) into ContactToRelationship

!insert (relationship1, person2) into RelationshipToContact
!insert (relationship2, person3) into RelationshipToContact
!insert (relationship3, company2) into RelationshipToContact

!insert (person1, address1) into ContactContainsAddress
!insert (person2, address2) into ContactContainsAddress
!insert (person3, address3) into ContactContainsAddress

!new Person('person4')
!person4.name := 'David'
!person4.phone := '111-222-3333'
!person4.website := 'www.david.com'
!person4.email := 'david@example.com'
!person4.title := 'Intern'

!insert (addressBook1, person4) into AddressBookMadeOfContact

!new Note('note4')
!note4.author := 'David'
!note4.time := Date('2023-10-08')
!note4.type := #EMAIL
!note4.comment := 'Email manager about progress'

!insert (person4, note4) into ContactContainsNote

!new Address('address4')
!address4.city := 'Chicago'
!address4.houseNr := '10'
!address4.street := 'Michigan Avenue'

!insert (person4, address4) into ContactContainsAddress

!new Company('company3')
!company3.name := 'Edu Corp'
!company3.phone := '888-999-0000'
!company3.website := 'www.educorp.com'
!company3.email := 'contact@educorp.com'
!company3.industry := 'Education'

!insert (addressBook1, company3) into AddressBookMadeOfContact

!new Relationship('relationship4')
!relationship4.type := #EMPLOYEE

!insert (company3, relationship4) into ContactToRelationship
!insert (relationship4, person4) into RelationshipToContact

!new Address('address5')
!address5.city := 'Boston'
!address5.houseNr := '303'
!address5.street := 'Beacon Street'

!new Address('address6')
!address6.city := 'Miami'
!address6.houseNr := '404'
!address6.street := 'Ocean Drive'

!insert (company1, address5) into ContactContainsAddress
!insert (company2, address6) into ContactContainsAddress

!new Note('note5')
!note5.author := 'Linda'
!note5.time := Date('2023-10-09')
!note5.type := #MEETING
!note5.comment := 'Meeting with the board'

!new Person('person5')
!person5.name := 'Linda'
!person5.phone := '101-202-3030'
!person5.website := 'www.linda.com'
!person5.email := 'linda@example.com'
!person5.title := 'Director'

!insert (addressBook1, person5) into AddressBookMadeOfContact
!insert (person5, note5) into ContactContainsNote

!new Relationship('relationship5')
!relationship5.type := #EMPLOYEE

!insert (person1, relationship5) into ContactToRelationship
!insert (relationship5, person5) into RelationshipToContact

!new Address('address7')
!address7.city := 'Denver'
!address7.houseNr := '707'
!address7.street := 'Colfax Avenue'

!insert (person5, address7) into ContactContainsAddress

!new Note('note6')
!note6.author := 'Lisa'
!note6.time := Date('2023-10-10')
!note6.type := #CALL
!note6.comment := 'Call with supplier'

!new Person('person6')
!person6.name := 'Lisa'
!person6.phone := '303-404-5050'
!person6.website := 'www.lisa.com'
!person6.email := 'lisa@example.com'
!person6.title := 'Scheduler'

!insert (addressBook1, person6) into AddressBookMadeOfContact
!insert (person6, note6) into ContactContainsNote

!new Address('address8')
!address8.city := 'Seattle'
!address8.houseNr := '808'
!address8.street := 'Pike Street'

!insert (person6, address8) into ContactContainsAddress

!new Relationship('relationship6')
!relationship6.type := #COWORKER

!insert (person6, relationship6) into ContactToRelationship
!insert (relationship6, person3) into RelationshipToContact
!new Person('person7')
!person7.name := 'Mark'
!person7.phone := '909-606-7070'
!person7.website := 'www.mark.com'
!person7.email := 'mark@example.com'
!person7.title := 'Analyst'

!insert (addressBook1, person7) into AddressBookMadeOfContact

!new Note('note7')
!note7.author := 'Mark'
!note7.time := Date('2023-10-11')
!note7.type := #MEETING
!note7.comment := 'Discuss analysis with team'

!insert (person7, note7) into ContactContainsNote

!new Address('address9')
!address9.city := 'Austin'
!address9.houseNr := '909'
!address9.street := 'Congress Avenue'

!insert (person7, address9) into ContactContainsAddress

!new Company('company4')
!company4.name := 'Retail Partners'
!company4.phone := '787-888-1111'
!company4.website := 'www.retailpartners.com'
!company4.email := 'info@retailpartners.com'
!company4.industry := 'Retail'

!insert (addressBook1, company4) into AddressBookMadeOfContact

!new Relationship('relationship7')
!relationship7.type := #SUBDIVISION

!insert (company4, relationship7) into ContactToRelationship
!insert (relationship7, company1) into RelationshipToContact

!new Note('note8')
!note8.author := 'Sarah'
!note8.time := Date('2023-10-12')
!note8.type := #CALL
!note8.comment := 'Call with prospective client'

!new Person('person8')
!person8.name := 'Sarah'
!person8.phone := '212-323-4343'
!person8.website := 'www.sarah.com'
!person8.email := 'sarah@example.com'
!person8.title := 'Consultant'

!insert (addressBook1, person8) into AddressBookMadeOfContact
!insert (person8, note8) into ContactContainsNote

!new Address('address10')
!address10.city := 'Philadelphia'
!address10.houseNr := '1010'
!address10.street := 'Chestnut Street'

!insert (person8, address10) into ContactContainsAddress

!new Relationship('relationship8')
!relationship8.type := #BOSS

!insert (person3, relationship8) into ContactToRelationship
!insert (relationship8, person8) into RelationshipToContact

!new Note('note9')
!note9.author := 'Tom'
!note9.time := Date('2023-10-13')
!note9.type := #EMAIL
!note9.comment := 'Email newsletter to subscribers'

!new Person('person9')
!person9.name := 'Tom'
!person9.phone := '424-535-6464'
!person9.website := 'www.tom.com'
!person9.email := 'tom@example.com'
!person9.title := 'Marketer'

!insert (addressBook1, person9) into AddressBookMadeOfContact
!insert (person9, note9) into ContactContainsNote

!new Address('address11')
!address11.city := 'Phoenix'
!address11.houseNr := '1111'
!address11.street := 'Camelback Road'

!insert (person9, address11) into ContactContainsAddress

!new Relationship('relationship9')
!relationship9.type := #EMPLOYEE

!insert (company2, relationship9) into ContactToRelationship
!insert (relationship9, person9) into RelationshipToContact

!new Note('note10')
!note10.author := 'Emma'
!note10.time := Date('2023-10-14')
!note10.type := #MEETING
!note10.comment := 'Team sync-up meeting'

!new Person('person10')
!person10.name := 'Emma'
!person10.phone := '636-747-8585'
!person10.website := 'www.emma.com'
!person10.email := 'emma@example.com'
!person10.title := 'Project Manager'

!insert (addressBook1, person10) into AddressBookMadeOfContact
!insert (person10, note10) into ContactContainsNote

!new Address('address12')
!address12.city := 'Houston'
!address12.houseNr := '1212'
!address12.street := 'Texas Avenue'

!insert (person10, address12) into ContactContainsAddress

!new Relationship('relationship10')
!relationship10.type := #COWORKER

!insert (person10, relationship10) into ContactToRelationship
!insert (relationship10, person5) into RelationshipToContact

```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 259 | 0.00% |
| Multiplicities Errors | 0 | 56 | 0.00% |
| Invariants Errors | 0 | 1 | 0.00% |

| AddressBook | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Phones | 0 | 14 | 0.00% |
| Websites | 0 | 14 | 0.00% |
| Emails | 0 | 14 | 0.00% |
| Addresses | 6 | 12 | 50.00% |

| Invalid Addresses | 
|---| 
```
Sunset Boulevard, 200, Los Angeles
```
```
Camelback Road, 1111, Phoenix
```
```
Market Street, 101, San Francisco
```
```
Colfax Avenue, 707, Denver
```
```
Ocean Drive, 404, Miami
```
```
Michigan Avenue, 10, Chicago
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | addressbook | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 259 | 0.00% |
| Multiplicities Errors | 0 | 56 | 0.00% |
| Invariants Errors | 0 | 1 | 0.00% |

| AddressBook | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Phones | 0 | 14 | 0.00% |
| Websites | 0 | 14 | 0.00% |
| Emails | 0 | 14 | 0.00% |
| Addresses | 6 | 12 | 50.00% |

| Invalid Addresses | 
|---| 
```
Sunset Boulevard, 200, Los Angeles
```
```
Camelback Road, 1111, Phoenix
```
```
Market Street, 101, San Francisco
```
```
Colfax Avenue, 707, Denver
```
```
Ocean Drive, 404, Miami
```
```
Michigan Avenue, 10, Chicago
```

