# Generation 1
```
!new AddressBook('addressBook2')

!new Person('person11')
!person11.name := 'Grace'
!person11.phone := '212-555-0911'
!person11.website := 'www.grace.com'
!person11.email := 'grace@example.com'
!person11.title := 'CEO'

!insert (addressBook2, person11) into AddressBookMadeOfContact

!new Person('person12')
!person12.name := 'Henry'
!person12.phone := '313-555-0922'
!person12.website := 'www.henry.com'
!person12.email := 'henry@example.com'
!person12.title := 'CTO'

!insert (addressBook2, person12) into AddressBookMadeOfContact

!new Person('person13')
!person13.name := 'Ivy'
!person13.phone := '415-555-0933'
!person13.website := 'www.ivy.com'
!person13.email := 'ivy@example.com'
!person13.title := 'Head of Marketing'

!insert (addressBook2, person13) into AddressBookMadeOfContact

!new Company('company5')
!company5.name := 'Innovative Solutions'
!company5.phone := '555-0944'
!company5.website := 'www.innovativesolutions.com'
!company5.email := 'contact@innovativesolutions.com'
!company5.industry := 'Consulting'

!insert (addressBook2, company5) into AddressBookMadeOfContact

!new Company('company6')
!company6.name := 'Financial Wiz'
!company6.phone := '666-0955'
!company6.website := 'www.financialwiz.com'
!company6.email := 'info@financialwiz.com'
!company6.industry := 'Finance'

!insert (addressBook2, company6) into AddressBookMadeOfContact

!new Address('address13')
!address13.city := 'Dallas'
!address13.houseNr := '111'
!address13.street := 'Main Street'

!insert (person11, address13) into ContactContainsAddress

!new Address('address14')
!address14.city := 'San Diego'
!address14.houseNr := '222'
!address14.street := 'Palm Avenue'

!insert (person12, address14) into ContactContainsAddress

!new Address('address15')
!address15.city := 'Sacramento'
!address15.houseNr := '333'
!address15.street := 'J Street'

!insert (person13, address15) into ContactContainsAddress

!new Address('address16')
!address16.city := 'Portland'
!address16.houseNr := '444'
!address16.street := 'Burnside Street'

!insert (company5, address16) into ContactContainsAddress

!new Address('address17')
!address17.city := 'Las Vegas'
!address17.houseNr := '555'
!address17.street := 'Vegas Strip'

!insert (company6, address17) into ContactContainsAddress

!new Note('note11')
!note11.author := 'Grace'
!note11.time := Date('2023-10-15')
!note11.type := #CALL
!note11.comment := 'Call with investors'

!insert (person11, note11) into ContactContainsNote

!new Note('note12')
!note12.author := 'Henry'
!note12.time := Date('2023-10-16')
!note12.type := #MEETING
!note12.comment := 'Meeting with the tech team'

!insert (person12, note12) into ContactContainsNote

!new Note('note13')
!note13.author := 'Ivy'
!note13.time := Date('2023-10-17')
!note13.type := #EMAIL
!note13.comment := 'Email newsletter to subscribers'

!insert (person13, note13) into ContactContainsNote

!new Note('note14')
!note14.author := 'Alice'
!note14.time := Date('2023-10-18')
!note14.type := #CALL
!note14.comment := 'Call to discuss quarterly results'

!new Person('person14')
!person14.name := 'Alice'
!person14.phone := '717-555-0944'
!person14.website := 'www.alice.com'
!person14.email := 'alice@example.com'
!person14.title := 'Analyst'

!insert (addressBook2, person14) into AddressBookMadeOfContact
!insert (person14, note14) into ContactContainsNote

!new Address('address18')
!address18.city := 'Boston'
!address18.houseNr := '666'
!address18.street := 'Boylston Street'

!insert (person14, address18) into ContactContainsAddress

!new Relationship('relationship11')
!relationship11.type := #BOSS

!insert (person11, relationship11) into ContactToRelationship
!insert (relationship11, person12) into RelationshipToContact

!new Relationship('relationship12')
!relationship12.type := #COWORKER

!insert (person13, relationship12) into ContactToRelationship
!insert (relationship12, person14) into RelationshipToContact

!new Relationship('relationship13')
!relationship13.type := #SUBDIVISION

!insert (company5, relationship13) into ContactToRelationship
!insert (relationship13, company6) into RelationshipToContact

!new Note('note15')
!note15.author := 'Frank'
!note15.time := Date('2023-10-19')
!note15.type := #EMAIL
!note15.comment := 'Email to confirm contract details'

!new Person('person15')
!person15.name := 'Frank'
!person15.phone := '818-555-0955'
!person15.website := 'www.frank.com'
!person15.email := 'frank@example.com'
!person15.title := 'HR Manager'

!insert (addressBook2, person15) into AddressBookMadeOfContact
!insert (person15, note15) into ContactContainsNote

!new Address('address19')
!address19.city := 'San Jose'
!address19.houseNr := '777'
!address19.street := 'Technology Drive'

!insert (person15, address19) into ContactContainsAddress

!new Relationship('relationship14')
!relationship14.type := #EMPLOYEE

!insert (company6, relationship14) into ContactToRelationship
!insert (relationship14, person15) into RelationshipToContact

!new Note('note16')
!note16.author := 'Nancy'
!note16.time := Date('2023-10-20')
!note16.type := #MEETING
!note16.comment := 'Meeting to discuss strategy'

!new Person('person16')
!person16.name := 'Nancy'
!person16.phone := '919-555-0966'
!person16.website := 'www.nancy.com'
!person16.email := 'nancy@example.com'
!person16.title := 'Strategist'

!insert (addressBook2, person16) into AddressBookMadeOfContact
!insert (person16, note16) into ContactContainsNote

!new Address('address20')
!address20.city := 'Orlando'
!address20.houseNr := '888'
!address20.street := 'Orange Avenue'

!insert (person16, address20) into ContactContainsAddress

!new AddressBook('addressBook2')

!new Person('person11')
!person11.name := 'Grace'
!person11.phone := '212-555-0911'
!person11.website := 'www.grace.com'
!person11.email := 'grace@example.com'
!person11.title := 'CEO'

!insert (addressBook2, person11) into AddressBookMadeOfContact

!new Person('person12')
!person12.name := 'Henry'
!person12.phone := '313-555-0922'
!person12.website := 'www.henry.com'
!person12.email := 'henry@example.com'
!person12.title := 'CTO'

!insert (addressBook2, person12) into AddressBookMadeOfContact

!new Person('person13')
!person13.name := 'Ivy'
!person13.phone := '415-555-0933'
!person13.website := 'www.ivy.com'
!person13.email := 'ivy@example.com'
!person13.title := 'Head of Marketing'

!insert (addressBook2, person13) into AddressBookMadeOfContact

!new Company('company5')
!company5.name := 'Innovative Solutions'
!company5.phone := '555-0944'
!company5.website := 'www.innovativesolutions.com'
!company5.email := 'contact@innovativesolutions.com'
!company5.industry := 'Consulting'

!insert (addressBook2, company5) into AddressBookMadeOfContact

!new Company('company6')
!company6.name := 'Financial Wiz'
!company6.phone := '666-0955'
!company6.website := 'www.financialwiz.com'
!company6.email := 'info@financialwiz.com'
!company6.industry := 'Finance'

!insert (addressBook2, company6) into AddressBookMadeOfContact

!new Address('address13')
!address13.city := 'Dallas'
!address13.houseNr := '111'
!address13.street := 'Main Street'

!insert (person11, address13) into ContactContainsAddress

!new Address('address14')
!address14.city := 'San Diego'
!address14.houseNr := '222'
!address14.street := 'Palm Avenue'

!insert (person12, address14) into ContactContainsAddress

!new Address('address15')
!address15.city := 'Sacramento'
!address15.houseNr := '333'
!address15.street := 'J Street'

!insert (person13, address15) into ContactContainsAddress

!new Address('address16')
!address16.city := 'Portland'
!address16.houseNr := '444'
!address16.street := 'Burnside Street'

!insert (company5, address16) into ContactContainsAddress

!new Address('address17')
!address17.city := 'Las Vegas'
!address17.houseNr := '555'
!address17.street := 'Vegas Strip'

!insert (company6, address17) into ContactContainsAddress

!new Note('note11')
!note11.author := 'Grace'
!note11.time := Date('2023-10-15')
!note11.type := #CALL
!note11.comment := 'Call with investors'

!insert (person11, note11) into ContactContainsNote

!new Note('note12')
!note12.author := 'Henry'
!note12.time := Date('2023-10-16')
!note12.type := #MEETING
!note12.comment := 'Meeting with the tech team'

!insert (person12, note12) into ContactContainsNote

!new Note('note13')
!note13.author := 'Ivy'
!note13.time := Date('2023-10-17')
!note13.type := #EMAIL
!note13.comment := 'Email newsletter to subscribers'

!insert (person13, note13) into ContactContainsNote

!new Note('note14')
!note14.author := 'Alice'
!note14.time := Date('2023-10-18')
!note14.type := #CALL
!note14.comment := 'Call to discuss quarterly results'

!new Person('person14')
!person14.name := 'Alice'
!person14.phone := '717-555-0944'
!person14.website := 'www.alice.com'
!person14.email := 'alice@example.com'
!person14.title := 'Analyst'

!insert (addressBook2, person14) into AddressBookMadeOfContact
!insert (person14, note14) into ContactContainsNote

!new Address('address18')
!address18.city := 'Boston'
!address18.houseNr := '666'
!address18.street := 'Boylston Street'

!insert (person14, address18) into ContactContainsAddress

!new Relationship('relationship11')
!relationship11.type := #BOSS

!insert (person11, relationship11) into ContactToRelationship
!insert (relationship11, person12) into RelationshipToContact

!new Relationship('relationship12')
!relationship12.type := #COWORKER

!insert (person13, relationship12) into ContactToRelationship
!insert (relationship12, person14) into RelationshipToContact

!new Relationship('relationship13')
!relationship13.type := #SUBDIVISION

!insert (company5, relationship13) into ContactToRelationship
!insert (relationship13, company6) into RelationshipToContact

!new Note('note15')
!note15.author := 'Frank'
!note15.time := Date('2023-10-19')
!note15.type := #EMAIL
!note15.comment := 'Email to confirm contract details'

!new Person('person15')
!person15.name := 'Frank'
!person15.phone := '818-555-0955'
!person15.website := 'www.frank.com'
!person15.email := 'frank@example.com'
!person15.title := 'HR Manager'

!insert (addressBook2, person15) into AddressBookMadeOfContact
!insert (person15, note15) into ContactContainsNote

!new Address('address19')
!address19.city := 'San Jose'
!address19.houseNr := '777'
!address19.street := 'Technology Drive'

!insert (person15, address19) into ContactContainsAddress

!new Relationship('relationship14')
!relationship14.type := #EMPLOYEE

!insert (company6, relationship14) into ContactToRelationship
!insert (relationship14, person15) into RelationshipToContact

!new Note('note16')
!note16.author := 'Nancy'
!note16.time := Date('2023-10-20')
!note16.type := #MEETING
!note16.comment := 'Meeting to discuss strategy'

!new Person('person16')
!person16.name := 'Nancy'
!person16.phone := '919-555-0966'
!person16.website := 'www.nancy.com'
!person16.email := 'nancy@example.com'
!person16.title := 'Strategist'

!insert (addressBook2, person16) into AddressBookMadeOfContact
!insert (person16, note16) into ContactContainsNote

!new Address('address20')
!address20.city := 'Orlando'
!address20.houseNr := '888'
!address20.street := 'Orange Avenue'

!insert (person16, address20) into ContactContainsAddress

!new Person('person17')
!person17.name := 'Oliver'
!person17.phone := '202-555-0977'
!person17.website := 'www.oliver.com'
!person17.email := 'oliver@example.com'
!person17.title := 'Designer'

!insert (addressBook2, person17) into AddressBookMadeOfContact

!new Address('address21')
!address21.city := 'Seattle'
!address21.houseNr := '999'
!address21.street := 'Pike Street'

!insert (person17, address21) into ContactContainsAddress

!new Note('note17')
!note17.author := 'Oliver'
!note17.time := Date('2023-10-21')
!note17.type := #CALL
!note17.comment := 'Call for design feedback'

!insert (person17, note17) into ContactContainsNote

!new Relationship('relationship15')
!relationship15.type := #COWORKER

!insert (person12, relationship15) into ContactToRelationship
!insert (relationship15, person17) into RelationshipToContact

!new Company('company7')
!company7.name := 'Tech Ventures'
!company7.phone := '101-555-0988'
!company7.website := 'www.techventures.com'
!company7.email := 'info@techventures.com'
!company7.industry := 'Technology'

!insert (addressBook2, company7) into AddressBookMadeOfContact

!new Address('address22')
!address22.city := 'Austin'
!address22.houseNr := '1010'
!address22.street := 'Congress Avenue'

!insert (company7, address22) into ContactContainsAddress

!new Relationship('relationship16')
!relationship16.type := #SUBDIVISION

!insert (company7, relationship16) into ContactToRelationship
!insert (relationship16, company5) into RelationshipToContact

!new AddressBook('addressBook3')

!new Person('person18')
!person18.name := 'Sophia'
!person18.phone := '323-555-0981'
!person18.website := 'www.sophia.com'
!person18.email := 'sophia@example.com'
!person18.title := 'Project Manager'

!insert (addressBook3, person18) into AddressBookMadeOfContact

!new Person('person19')
!person19.name := 'Liam'
!person19.phone := '454-555-0982'
!person19.website := 'www.liam.com'
!person19.email := 'liam@example.com'
!person19.title := 'Developer'

!insert (addressBook3, person19) into AddressBookMadeOfContact

!new Person('person20')
!person20.name := 'Emma'
!person20.phone := '565-555-0983'
!person20.website := 'www.emma.com'
!person20.email := 'emma@example.com'
!person20.title := 'Designer'

!insert (addressBook3, person20) into AddressBookMadeOfContact

!new Company('company8')
!company8.name := 'Design Co.'
!company8.phone := '676-555-0984'
!company8.website := 'www.designco.com'
!company8.email := 'contact@designco.com'
!company8.industry := 'Design'

!insert (addressBook3, company8) into AddressBookMadeOfContact

!new Address('address23')
!address23.city := 'Miami'
!address23.houseNr := '1111'
!address23.street := 'Ocean Drive'

!insert (person18, address23) into ContactContainsAddress

!new Address('address24')
!address24.city := 'Phoenix'
!address24.houseNr := '2222'
!address24.street := 'Central Avenue'

!insert (person19, address24) into ContactContainsAddress

!new Address('address25')
!address25.city := 'Denver'
!address25.houseNr := '3333'
!address25.street := 'Market Street'

!insert (person20, address25) into ContactContainsAddress

!new Address('address26')
!address26.city := 'Chicago'
!address26.houseNr := '4444'
!address26.street := 'Lakeshore Drive'

!insert (company8, address26) into ContactContainsAddress

!new Note('note18')
!note18.author := 'Sophia'
!note18.time := Date('2023-10-22')
!note18.type := #MEETING
!note18.comment := 'Project planning session'

!insert (person18, note18) into ContactContainsNote

!new Note('note19')
!note19.author := 'Liam'
!note19.time := Date('2023-10-23')
!note19.type := #CALL
!note19.comment := 'Tech support call'

!insert (person19, note19) into ContactContainsNote

!new Note('note20')
!note20.author := 'Emma'
!note20.time := Date('2023-10-24')
!note20.type := #EMAIL
!note20.comment := 'Design feedback email'

!insert (person20, note20) into ContactContainsNote

!new Relationship('relationship17')
!relationship17.type := #COWORKER

!insert (person18, relationship17) into ContactToRelationship
!insert (relationship17, person19) into RelationshipToContact

!new Relationship('relationship18')
!relationship18.type := #BOSS

!insert (person20, relationship18) into ContactToRelationship
!insert (relationship18, person18) into RelationshipToContact

!new Person('person21')
!person21.name := 'Noah'
!person21.phone := '676-555-0985'
!person21.website := 'www.noah.com'
!person21.email := 'noah@example.com'
!person21.title := 'Sales Manager'

!insert (addressBook3, person21) into AddressBookMadeOfContact

!new Address('address27')
!address27.city := 'Houston'
!address27.houseNr := '5555'
!address27.street := 'Main Plaza'

!insert (person21, address27) into ContactContainsAddress

!new Note('note21')
!note21.author := 'Noah'
!note21.time := Date('2023-10-25')
!note21.type := #EMAIL
!note21.comment := 'Sales report email'

!insert (person21, note21) into ContactContainsNote

!new Relationship('relationship19')
!relationship19.type := #EMPLOYEE

!insert (company8, relationship19) into ContactToRelationship
!insert (relationship19, person21) into RelationshipToContact

!new Person('person22')
!person22.name := 'Ava'
!person22.phone := '787-555-0986'
!person22.website := 'www.ava.com'
!person22.email := 'ava@example.com'
!person22.title := 'Operations Manager'

!insert (addressBook3, person22) into AddressBookMadeOfContact

!new Address('address28')
!address28.city := 'Atlanta'
!address28.houseNr := '6666'
!address28.street := 'Peachtree Street'

!insert (person22, address28) into ContactContainsAddress

!new Note('note22')
!note22.author := 'Ava'
!note22.time := Date('2023-10-26')
!note22.type := #MEETING
!note22.comment := 'Operations meeting agenda'

!insert (person22, note22) into ContactContainsNote

!new Relationship('relationship20')
!relationship20.type := #SUBDIVISION

!insert (company8, relationship20) into ContactToRelationship
!insert (relationship20, company8) into RelationshipToContact

!new Company('company9')
!company9.name := 'Health Solutions'
!company9.phone := '898-555-0989'
!company9.website := 'www.healthsolutions.com'
!company9.email := 'info@healthsolutions.com'
!company9.industry := 'Healthcare'

!insert (addressBook3, company9) into AddressBookMadeOfContact

!new Address('address29')
!address29.city := 'Baltimore'
!address29.houseNr := '7777'
!address29.street := 'Harborview Avenue'

!insert (company9, address29) into ContactContainsAddress

!new Note('note23')
!note23.author := 'Evelyn'
!note23.time := Date('2023-10-27')
!note23.type := #CALL
!note23.comment := 'Call with hospital admin'

!new Person('person23')
!person23.name := 'Evelyn'
!person23.phone := '909-555-0987'
!person23.website := 'www.evelyn.com'
!person23.email := 'evelyn@example.com'
!person23.title := 'Healthcare Coordinator'

!insert (addressBook3, person23) into AddressBookMadeOfContact
!insert (person23, note23) into ContactContainsNote

!new Address('address30')
!address30.city := 'Pittsburgh'
!address30.houseNr := '8888'
!address30.street := 'Liberty Avenue'

!insert (person23, address30) into ContactContainsAddress

!new Relationship('relationship21')
!relationship21.type := #BOSS

!insert (person23, relationship21) into ContactToRelationship
!insert (relationship21, person22) into RelationshipToContact

!new Person('person24')
!person24.name := 'Lucas'
!person24.phone := '1010-555-0990'
!person24.website := 'www.lucas.com'
!person24.email := 'lucas@example.com'
!person24.title := 'Marketing Specialist'

!insert (addressBook3, person24) into AddressBookMadeOfContact

!new Address('address31')
!address31.city := 'New Orleans'
!address31.houseNr := '9999'
!address31.street := 'Canal Street'

!insert (person24, address31) into ContactContainsAddress

!new Note('note24')
!note24.author := 'Lucas'
!note24.time := Date('2023-10-28')
!note24.type := #EMAIL
!note24.comment := 'Marketing strategy email'

!insert (person24, note24) into ContactContainsNote

!new Relationship('relationship22')
!relationship22.type := #COWORKER

!insert (person21, relationship22) into ContactToRelationship
!insert (relationship22, person24) into RelationshipToContact

!new Company('company10')
!company10.name := 'Eco Ventures'
!company10.phone := '111-555-0991'
!company10.website := 'www.ecoventures.com'
!company10.email := 'support@ecoventures.com'
!company10.industry := 'Environmental'

!insert (addressBook3, company10) into AddressBookMadeOfContact

!new Address('address32')
!address32.city := 'San Francisco'
!address32.houseNr := '10101'
!address32.street := 'Lombard Street'

!insert (company10, address32) into ContactContainsAddress

!new Note('note25')
!note25.author := 'Mia'
!note25.time := Date('2023-10-29')
!note25.type := #MEETING
!note25.comment := 'Eco initiatives meeting'

!new Person('person25')
!person25.name := 'Mia'
!person25.phone := '1212-555-0992'
!person25.website := 'www.mia.com'
!person25.email := 'mia@example.com'
!person25.title := 'Eco Consultant'

!insert (addressBook3, person25) into AddressBookMadeOfContact
!insert (person25, note25) into ContactContainsNote

!new Address('address33')
!address33.city := 'San Francisco'
!address33.houseNr := '11112'
!address33.street := 'Hillside Avenue'

!insert (person25, address33) into ContactContainsAddress

!new Relationship('relationship23')
!relationship23.type := #BOSS

!insert (company10, relationship23) into ContactToRelationship
!insert (relationship23, person25) into RelationshipToContact

!new Note('note26')
!note26.author := 'Sophia'
!note26.time := Date('2023-10-30')
!note26.type := #EMAIL
!note26.comment := 'Email updates on projects'

!insert (person18, note26) into ContactContainsNote

!new Note('note27')
!note27.author := 'Liam'
!note27.time := Date('2023-10-31')
!note27.type := #CALL
!note27.comment := 'Call to discuss features'

!insert (person19, note27) into ContactContainsNote

!new Person('person26')
!person26.name := 'Olivia'
!person26.phone := '1313-555-0993'
!person26.website := 'www.olivia.com'
!person26.email := 'olivia@example.com'
!person26.title := 'Product Manager'

!insert (addressBook3, person26) into AddressBookMadeOfContact

!new Address('address34')
!address34.city := 'Nashville'
!address34.houseNr := '12121'
!address34.street := 'Broadway'

!insert (person26, address34) into ContactContainsAddress

!new Note('note28')
!note28.author := 'Olivia'
!note28.time := Date('2023-11-01')
!note28.type := #MEETING
!note28.comment := 'Product launch meeting'

!insert (person26, note28) into ContactContainsNote

!new Relationship('relationship24')
!relationship24.type := #COWORKER

!insert (person24, relationship24) into ContactToRelationship
!insert (relationship24, person26) into RelationshipToContact

!new Company('company11')
!company11.name := 'Architect Innovations'
!company11.phone := '1414-555-0994'
!company11.website := 'www.architectinnovations.com'
!company11.email := 'contact@architectinnovations.com'
!company11.industry := 'Architecture'

!insert (addressBook3, company11) into AddressBookMadeOfContact

!new Address('address35')
!address35.city := 'Salt Lake City'
!address35.houseNr := '13131'
!address35.street := 'Temple Street'

!insert (company11, address35) into ContactContainsAddress

!new Note('note29')
!note29.author := 'James'
!note29.time := Date('2023-11-02')
!note29.type := #EMAIL
!note29.comment := 'Email to confirm designs'

!new Person('person27') 
!person27.name := 'James' 
!person27.phone := '1515-555-0995' 
!person27.website := 'www.james.com' 
!person27.email := 'james@example.com' 
!person27.title := 'Architect'

!insert (addressBook3, person27) into AddressBookMadeOfContact
!insert (person27, note29) into ContactContainsNote

!new Address('address36')
!address36.city := 'Boise'
!address36.houseNr := '14141'
!address36.street := 'Capitol Avenue'

!insert (person27, address36) into ContactContainsAddress

!new Relationship('relationship25')
!relationship25.type := #EMPLOYEE

!insert (company11, relationship25) into ContactToRelationship
!insert (relationship25, person27) into RelationshipToContact

-- Done creating 40 more entities

```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 56 | 613 | 9.14% |
| Multiplicities Errors | 0 | 127 | 0.00% |
| Invariants Errors | 1 | 1 | 100.00% |

| Syntax Errors | 
|---| 
```
Error: An object with name `addressBook2' already exists.
```
```
Error: An object with name `person11' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person11) already exist.
```
```
Error: An object with name `person12' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person12) already exist.
```
```
Error: An object with name `person13' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person13) already exist.
```
```
Error: An object with name `company5' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,company5) already exist.
```
```
Error: An object with name `company6' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,company6) already exist.
```
```
Error: An object with name `address13' already exists.
```
```
Error: Link `ContactContainsAddress' between (person11,address13) already exist.
```
```
Error: An object with name `address14' already exists.
```
```
Error: Link `ContactContainsAddress' between (person12,address14) already exist.
```
```
Error: An object with name `address15' already exists.
```
```
Error: Link `ContactContainsAddress' between (person13,address15) already exist.
```
```
Error: An object with name `address16' already exists.
```
```
Error: Link `ContactContainsAddress' between (company5,address16) already exist.
```
```
Error: An object with name `address17' already exists.
```
```
Error: Link `ContactContainsAddress' between (company6,address17) already exist.
```
```
Error: An object with name `note11' already exists.
```
```
Error: Link `ContactContainsNote' between (person11,note11) already exist.
```
```
Error: An object with name `note12' already exists.
```
```
Error: Link `ContactContainsNote' between (person12,note12) already exist.
```
```
Error: An object with name `note13' already exists.
```
```
Error: Link `ContactContainsNote' between (person13,note13) already exist.
```
```
Error: An object with name `note14' already exists.
```
```
Error: An object with name `person14' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person14) already exist.
```
```
Error: Link `ContactContainsNote' between (person14,note14) already exist.
```
```
Error: An object with name `address18' already exists.
```
```
Error: Link `ContactContainsAddress' between (person14,address18) already exist.
```
```
Error: An object with name `relationship11' already exists.
```
```
Error: Link `ContactToRelationship' between (person11,relationship11) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship11,person12) already exist.
```
```
Error: An object with name `relationship12' already exists.
```
```
Error: Link `ContactToRelationship' between (person13,relationship12) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship12,person14) already exist.
```
```
Error: An object with name `relationship13' already exists.
```
```
Error: Link `ContactToRelationship' between (company5,relationship13) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship13,company6) already exist.
```
```
Error: An object with name `note15' already exists.
```
```
Error: An object with name `person15' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person15) already exist.
```
```
Error: Link `ContactContainsNote' between (person15,note15) already exist.
```
```
Error: An object with name `address19' already exists.
```
```
Error: Link `ContactContainsAddress' between (person15,address19) already exist.
```
```
Error: An object with name `relationship14' already exists.
```
```
Error: Link `ContactToRelationship' between (company6,relationship14) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship14,person15) already exist.
```
```
Error: An object with name `note16' already exists.
```
```
Error: An object with name `person16' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person16) already exist.
```
```
Error: Link `ContactContainsNote' between (person16,note16) already exist.
```
```
Error: An object with name `address20' already exists.
```

| Invariants Errors | 
|---| 
```
checking invariant (1) `Contact::DifferentSourceTarget': FAILED.
```

| AddressBook | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Phones | 0 | 24 | 0.00% |
| Websites | 1 | 24 | 4.17% |
| Emails | 1 | 24 | 4.17% |
| Addresses | 20 | 24 | 83.33% |

| Invalid Websites | 
|---| 
```
www.james.com 
```

| Invalid Emails | 
|---| 
```
james@example.com 
```

| Invalid Addresses | 
|---| 
```
Liberty Avenue, 8888, Pittsburgh
```
```
Orange Avenue, 888, Orlando
```
```
Canal Street, 9999, New Orleans
```
```
Lombard Street, 10101, San Francisco
```
```
Hillside Avenue, 11112, San Francisco
```
```
Ocean Drive, 1111, Miami
```
```
Broadway, 12121, Nashville
```
```
Main Street, 111, Dallas
```
```
Central Avenue, 2222, Phoenix
```
```
Temple Street, 13131, Salt Lake City
```
```
Palm Avenue, 222, San Diego
```
```
Market Street, 3333, Denver
```
```
Capitol Avenue, 14141, Boise
```
```
Lakeshore Drive, 4444, Chicago
```
```
Burnside Street, 444, Portland
```
```
Main Plaza, 5555, Houston
```
```
Vegas Strip, 555, Las Vegas
```
```
Peachtree Street, 6666, Atlanta
```
```
Harborview Avenue, 7777, Baltimore
```
```
Technology Drive, 777, San Jose
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
| Syntax Errors | 56 | 613 | 9.14% |
| Multiplicities Errors | 0 | 127 | 0.00% |
| Invariants Errors | 1 | 1 | 100.00% |

| Syntax Errors | 
|---| 
```
Error: An object with name `addressBook2' already exists.
```
```
Error: An object with name `person11' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person11) already exist.
```
```
Error: An object with name `person12' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person12) already exist.
```
```
Error: An object with name `person13' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person13) already exist.
```
```
Error: An object with name `company5' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,company5) already exist.
```
```
Error: An object with name `company6' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,company6) already exist.
```
```
Error: An object with name `address13' already exists.
```
```
Error: Link `ContactContainsAddress' between (person11,address13) already exist.
```
```
Error: An object with name `address14' already exists.
```
```
Error: Link `ContactContainsAddress' between (person12,address14) already exist.
```
```
Error: An object with name `address15' already exists.
```
```
Error: Link `ContactContainsAddress' between (person13,address15) already exist.
```
```
Error: An object with name `address16' already exists.
```
```
Error: Link `ContactContainsAddress' between (company5,address16) already exist.
```
```
Error: An object with name `address17' already exists.
```
```
Error: Link `ContactContainsAddress' between (company6,address17) already exist.
```
```
Error: An object with name `note11' already exists.
```
```
Error: Link `ContactContainsNote' between (person11,note11) already exist.
```
```
Error: An object with name `note12' already exists.
```
```
Error: Link `ContactContainsNote' between (person12,note12) already exist.
```
```
Error: An object with name `note13' already exists.
```
```
Error: Link `ContactContainsNote' between (person13,note13) already exist.
```
```
Error: An object with name `note14' already exists.
```
```
Error: An object with name `person14' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person14) already exist.
```
```
Error: Link `ContactContainsNote' between (person14,note14) already exist.
```
```
Error: An object with name `address18' already exists.
```
```
Error: Link `ContactContainsAddress' between (person14,address18) already exist.
```
```
Error: An object with name `relationship11' already exists.
```
```
Error: Link `ContactToRelationship' between (person11,relationship11) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship11,person12) already exist.
```
```
Error: An object with name `relationship12' already exists.
```
```
Error: Link `ContactToRelationship' between (person13,relationship12) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship12,person14) already exist.
```
```
Error: An object with name `relationship13' already exists.
```
```
Error: Link `ContactToRelationship' between (company5,relationship13) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship13,company6) already exist.
```
```
Error: An object with name `note15' already exists.
```
```
Error: An object with name `person15' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person15) already exist.
```
```
Error: Link `ContactContainsNote' between (person15,note15) already exist.
```
```
Error: An object with name `address19' already exists.
```
```
Error: Link `ContactContainsAddress' between (person15,address19) already exist.
```
```
Error: An object with name `relationship14' already exists.
```
```
Error: Link `ContactToRelationship' between (company6,relationship14) already exist.
```
```
Error: Link `RelationshipToContact' between (relationship14,person15) already exist.
```
```
Error: An object with name `note16' already exists.
```
```
Error: An object with name `person16' already exists.
```
```
Error: Link `AddressBookMadeOfContact' between (addressBook2,person16) already exist.
```
```
Error: Link `ContactContainsNote' between (person16,note16) already exist.
```
```
Error: An object with name `address20' already exists.
```

| Invariants Errors | 
|---| 
```
checking invariant (1) `Contact::DifferentSourceTarget': FAILED.
```

| AddressBook | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Phones | 0 | 24 | 0.00% |
| Websites | 1 | 24 | 4.17% |
| Emails | 1 | 24 | 4.17% |
| Addresses | 20 | 24 | 83.33% |

| Invalid Websites | 
|---| 
```
www.james.com 
```

| Invalid Emails | 
|---| 
```
james@example.com 
```

| Invalid Addresses | 
|---| 
```
Liberty Avenue, 8888, Pittsburgh
```
```
Orange Avenue, 888, Orlando
```
```
Canal Street, 9999, New Orleans
```
```
Lombard Street, 10101, San Francisco
```
```
Hillside Avenue, 11112, San Francisco
```
```
Ocean Drive, 1111, Miami
```
```
Broadway, 12121, Nashville
```
```
Main Street, 111, Dallas
```
```
Central Avenue, 2222, Phoenix
```
```
Temple Street, 13131, Salt Lake City
```
```
Palm Avenue, 222, San Diego
```
```
Market Street, 3333, Denver
```
```
Capitol Avenue, 14141, Boise
```
```
Lakeshore Drive, 4444, Chicago
```
```
Burnside Street, 444, Portland
```
```
Main Plaza, 5555, Houston
```
```
Vegas Strip, 555, Las Vegas
```
```
Peachtree Street, 6666, Atlanta
```
```
Harborview Avenue, 7777, Baltimore
```
```
Technology Drive, 777, San Jose
```

