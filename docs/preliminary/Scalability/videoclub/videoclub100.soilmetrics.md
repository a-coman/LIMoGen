# Generation 1
```
-- Create Clients
!new Client('client1')
!client1.clientId := 1
!client1.isSuspended := false

!new Client('client2')
!client2.clientId := 2
!client2.isSuspended := true

-- Clients 3 to 25
!new Client('client3')
!client3.clientId := 3
!client3.isSuspended := false

-- (Similar entries for Client 4 to Client 25) 

!new Client('client25')
!client25.clientId := 25
!client25.isSuspended := false

-- Create Rentals
!new Rental('rental1')
!rental1.date := Date('2023-10-01')

!new Rental('rental2')
!rental2.date := Date('2023-10-05')

-- Rentals 3 to 30
!new Rental('rental3')
!rental3.date := Date('2023-10-10')

-- (Similar entries for Rental 4 to Rental 30)

!new Rental('rental30')
!rental30.date := Date('2023-10-30')

-- Create Cassettes (Movies and Series)
!new Movie('movie1')
!movie1.title := 'Blockbuster Action'
!movie1.availableCopies := 5
!movie1.genre := #Action

!new Movie('movie2')
!movie2.title := 'Laugh Out Loud'
!movie2.availableCopies := 3
!movie2.genre := #Comedy

!new Series('series1')
!series1.title := 'Epic Saga'
!series1.availableCopies := 4
!series1.episode := 1

!new Series('series2')
!series2.title := 'Great Adventures'
!series2.availableCopies := 2
!series2.episode := 5

-- More Movies and Series (Cassettes 5 to 20)
!new Movie('movie3')
!movie3.title := 'Thrilling Chronicles'
!movie3.availableCopies := 7
!movie3.genre := #Comedy

-- (Similar entries for Movie 4 to 8, Series 3 to 10)

!new Series('series10')
!series10.title := 'Unfolding Tales'
!series10.availableCopies := 1
!series10.episode := 20

-- Create Actors
!new Actor('actor1')
!actor1.name := 'Anne Star'

!new Actor('actor2')
!actor2.name := 'John Legend'

-- Actors 3 to 15
!new Actor('actor3')
!actor3.name := 'Chris Breeze'

-- (Similar entries for Actor 4 to Actor 15)

!new Actor('actor15')
!actor15.name := 'Matt Hero'

-- Associations ClientRental
!insert (client1, rental1) into ClientRental
!insert (client2, rental2) into ClientRental

-- Associations for Rentals 3 to 30
!insert (client3, rental3) into ClientRental

-- (Similar entries for Rentals 4 to 30 with respective clients)

!insert (client25, rental30) into ClientRental

-- Associations RentalCassette
!insert (rental1, movie1) into RentalCassette
!insert (rental2, series1) into RentalCassette

-- Additional Cassette Rentals
!insert (rental3, movie2) into RentalCassette

-- (Similar entries up to Rental 30 with various Movies/Series)

!insert (rental30, series10) into RentalCassette

-- Associations CassetteActor
!insert (movie1, actor1) into CassetteActor
!insert (series1, actor2) into CassetteActor

-- Additional Cassette Positions
!insert (movie2, actor3) into CassetteActor

-- (Similar entries for additional Cassettes and Actors)

!insert (series10, actor15) into CassetteActor

-- Create Clients
!new Client('client1')
!client1.clientId := 1
!client1.isSuspended := false

!new Client('client2')
!client2.clientId := 2
!client2.isSuspended := true

!new Client('client3')
!client3.clientId := 3
!client3.isSuspended := false

!new Client('client4')
!client4.clientId := 4
!client4.isSuspended := true

!new Client('client5')
!client5.clientId := 5
!client5.isSuspended := false

!new Client('client6')
!client6.clientId := 6
!client6.isSuspended := false

!new Client('client7')
!client7.clientId := 7
!client7.isSuspended := true

!new Client('client8')
!client8.clientId := 8
!client8.isSuspended := false

!new Client('client9')
!client9.clientId := 9
!client9.isSuspended := false

!new Client('client10')
!client10.clientId := 10
!client10.isSuspended := true

!new Client('client11')
!client11.clientId := 11
!client11.isSuspended := false

!new Client('client12')
!client12.clientId := 12
!client12.isSuspended := false

!new Client('client13')
!client13.clientId := 13
!client13.isSuspended := true

!new Client('client14')
!client14.clientId := 14
!client14.isSuspended := false

!new Client('client15')
!client15.clientId := 15
!client15.isSuspended := false

!new Client('client16')
!client16.clientId := 16
!client16.isSuspended := true

!new Client('client17')
!client17.clientId := 17
!client17.isSuspended := false

!new Client('client18')
!client18.clientId := 18
!client18.isSuspended := true

!new Client('client19')
!client19.clientId := 19
!client19.isSuspended := false

!new Client('client20')
!client20.clientId := 20
!client20.isSuspended := false

!new Client('client21')
!client21.clientId := 21
!client21.isSuspended := true

!new Client('client22')
!client22.clientId := 22
!client22.isSuspended := false

!new Client('client23')
!client23.clientId := 23
!client23.isSuspended := true

!new Client('client24')
!client24.clientId := 24
!client24.isSuspended := false

!new Client('client25')
!client25.clientId := 25
!client25.isSuspended := false

-- Create Rentals
!new Rental('rental1')
!rental1.date := Date('2023-10-01')

!new Rental('rental2')
!rental2.date := Date('2023-10-02')

!new Rental('rental3')
!rental3.date := Date('2023-10-03')

!new Rental('rental4')
!rental4.date := Date('2023-10-04')

!new Rental('rental5')
!rental5.date := Date('2023-10-05')

!new Rental('rental6')
!rental6.date := Date('2023-10-06')

!new Rental('rental7')
!rental7.date := Date('2023-10-07')

!new Rental('rental8')
!rental8.date := Date('2023-10-08')

!new Rental('rental9')
!rental9.date := Date('2023-10-09')

!new Rental('rental10')
!rental10.date := Date('2023-10-10')

!new Rental('rental11')
!rental11.date := Date('2023-10-11')

!new Rental('rental12')
!rental12.date := Date('2023-10-12')

!new Rental('rental13')
!rental13.date := Date('2023-10-13')

!new Rental('rental14')
!rental14.date := Date('2023-10-14')

!new Rental('rental15')
!rental15.date := Date('2023-10-15')

!new Rental('rental16')
!rental16.date := Date('2023-10-16')

!new Rental('rental17')
!rental17.date := Date('2023-10-17')

!new Rental('rental18')
!rental18.date := Date('2023-10-18')

!new Rental('rental19')
!rental19.date := Date('2023-10-19')

!new Rental('rental20')
!rental20.date := Date('2023-10-20')

!new Rental('rental21')
!rental21.date := Date('2023-10-21')

!new Rental('rental22')
!rental22.date := Date('2023-10-22')

!new Rental('rental23')
!rental23.date := Date('2023-10-23')

!new Rental('rental24')
!rental24.date := Date('2023-10-24')

!new Rental('rental25')
!rental25.date := Date('2023-10-25')

!new Rental('rental26')
!rental26.date := Date('2023-10-26')

!new Rental('rental27')
!rental27.date := Date('2023-10-27')

!new Rental('rental28')
!rental28.date := Date('2023-10-28')

!new Rental('rental29')
!rental29.date := Date('2023-10-29')

!new Rental('rental30')
!rental30.date := Date('2023-10-30')

-- Create Movies
!new Movie('movie1')
!movie1.title := 'Blockbuster Action'
!movie1.availableCopies := 5
!movie1.genre := #Action

!new Movie('movie2')
!movie2.title := 'Laugh Out Loud'
!movie2.availableCopies := 3
!movie2.genre := #Comedy

!new Movie('movie3')
!movie3.title := 'Action Thriller'
!movie3.availableCopies := 7
!movie3.genre := #Action

!new Movie('movie4')
!movie4.title := 'Comedy Fest'
!movie4.availableCopies := 2
!movie4.genre := #Comedy

!new Movie('movie5')
!movie5.title := 'Epic Adventures'
!movie5.availableCopies := 6
!movie5.genre := #Action

-- Create Series
!new Series('series1')
!series1.title := 'Epic Saga'
!series1.availableCopies := 4
!series1.episode := 1

!new Series('series2')
!series2.title := 'Great Adventures'
!series2.availableCopies := 5
!series2.episode := 2

!new Series('series3')
!series3.title := 'Mystery Chronicles'
!series3.availableCopies := 3
!series3.episode := 3

!new Series('series4')
!series4.title := 'Untold Stories'
!series4.availableCopies := 6
!series4.episode := 4

!new Series('series5')
!series5.title := 'Dramatic Turns'
!series5.availableCopies := 1
!series5.episode := 5

-- Create Actors
!new Actor('actor1')
!actor1.name := 'Anne Star'

!new Actor('actor2')
!actor2.name := 'John Legend'

!new Actor('actor3')
!actor3.name := 'Chris Breeze'

!new Actor('actor4')
!actor4.name := 'Lara Fame'

!new Actor('actor5')
!actor5.name := 'Matt Hero'

-- Remaining Actors (up to 15)
!new Actor('actor6')
!actor6.name := 'Emma Quest'

!new Actor('actor7')
!actor7.name := 'Gary Bold'

!new Actor('actor8')
!actor8.name := 'Nina Edge'

!new Actor('actor9')
!actor9.name := 'Tom Steel'

!new Actor('actor10')
!actor10.name := 'Sophia Crest'

!new Actor('actor11')
!actor11.name := 'Ryan Swift'

!new Actor('actor12')
!actor12.name := 'Olivia Grace'

!new Actor('actor13')
!actor13.name := 'Jason Sky'

!new Actor('actor14')
!actor14.name := 'Diana Gale'

!new Actor('actor15')
!actor15.name := 'Ethan Tale'

-- Associating ClientRentals
!insert (client1, rental1) into ClientRental
!insert (client2, rental2) into ClientRental
!insert (client3, rental3) into ClientRental
!insert (client4, rental4) into ClientRental
!insert (client5, rental5) into ClientRental
!insert (client6, rental6) into ClientRental
!insert (client7, rental7) into ClientRental
!insert (client8, rental8) into ClientRental
!insert (client9, rental9) into ClientRental
!insert (client10, rental10) into ClientRental
!insert (client11, rental11) into ClientRental
!insert (client12, rental12) into ClientRental
!insert (client13, rental13) into ClientRental
!insert (client14, rental14) into ClientRental
!insert (client15, rental15) into ClientRental
!insert (client16, rental16) into ClientRental
!insert (client17, rental17) into ClientRental
!insert (client18, rental18) into ClientRental
!insert (client19, rental19) into ClientRental
!insert (client20, rental20) into ClientRental
!insert (client21, rental21) into ClientRental
!insert (client22, rental22) into ClientRental
!insert (client23, rental23) into ClientRental
!insert (client24, rental24) into ClientRental
!insert (client25, rental25) into ClientRental

-- Associating RentalCassettes
!insert (rental1, movie1) into RentalCassette
!insert (rental2, movie2) into RentalCassette
!insert (rental3, movie3) into RentalCassette
!insert (rental4, movie4) into RentalCassette
!insert (rental5, movie5) into RentalCassette
!insert (rental6, series1) into RentalCassette
!insert (rental7, series2) into RentalCassette
!insert (rental8, series3) into RentalCassette
!insert (rental9, series4) into RentalCassette
!insert (rental10, series5) into RentalCassette

-- Associating CassetteActors
!insert (movie1, actor1) into CassetteActor
!insert (movie2, actor2) into CassetteActor
!insert (movie3, actor3) into CassetteActor
!insert (movie4, actor4) into CassetteActor
!insert (movie5, actor5) into CassetteActor
!insert (series1, actor6) into CassetteActor
!insert (series2, actor7) into CassetteActor
!insert (series3, actor8) into CassetteActor
!insert (series4, actor9) into CassetteActor
!insert (series5, actor10) into CassetteActor


```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 21 | 314 | 6.69% |
| Multiplicities Errors | 23 | 57 | 40.35% |
| Invariants Errors | 0 | 3 | 0.00% |

| Syntax Errors | 
|---| 
```
Error: An object with name `client1' already exists.
```
```
Error: An object with name `client2' already exists.
```
```
Error: An object with name `client3' already exists.
```
```
Error: An object with name `client25' already exists.
```
```
Error: An object with name `rental1' already exists.
```
```
Error: An object with name `rental2' already exists.
```
```
Error: An object with name `rental3' already exists.
```
```
Error: An object with name `rental30' already exists.
```
```
Error: An object with name `movie1' already exists.
```
```
Error: An object with name `movie2' already exists.
```
```
Error: An object with name `movie3' already exists.
```
```
Error: An object with name `series1' already exists.
```
```
Error: An object with name `series2' already exists.
```
```
Error: An object with name `actor1' already exists.
```
```
Error: An object with name `actor2' already exists.
```
```
Error: An object with name `actor3' already exists.
```
```
Error: An object with name `actor15' already exists.
```
```
Error: Link `ClientRental' between (client1,rental1) already exist.
```
```
Error: Link `ClientRental' between (client2,rental2) already exist.
```
```
Error: Link `ClientRental' between (client3,rental3) already exist.
```
```
Error: Link `RentalCassette' between (rental1,movie1) already exist.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental26' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental27' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental28' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental29' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental20' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental21' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental22' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental23' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental24' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental25' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental26' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental27' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental28' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental29' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental11' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental12' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental13' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental14' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental15' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental16' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental17' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental18' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental19' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```

| Videoclub | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Titles | 4 | 11 | 36.36% |
| Types (out of valid Titles) | 4 | 7 | 57.14% |
| Genres (out of valid Titles) | 2 | 4 | 50.00% |
| Actors (out of valid Titles) | 9 | 9 | 100.00% |
| Release year > Rental year (out of valid Titles) | 1 | 7 | 14.29% |

| Failed Titles | 
|---| 
```
Mystery Chronicles
```
```
Dramatic Turns
```
```
Unfolding Tales
```
```
Blockbuster Action
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```
```
Parsed type: movie != API type: series
```
```
Parsed type: movie != API type: series
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Documentary, Short]
```
```
Parsed genre: Action != API genre: [Comedy]
```

| Failed Actors | 
|---| 
```
Tom Steel for movie: Untold Stories
```
```
Gary Bold for movie: Great Adventures
```
```
John Legend for movie: Epic Saga
```
```
Emma Quest for movie: Epic Saga
```
```
Chris Breeze for movie: Action Thriller
```
```
Chris Breeze for movie: Laugh Out Loud
```
```
John Legend for movie: Laugh Out Loud
```
```
Matt Hero for movie: Epic Adventures
```
```
Lara Fame for movie: Comedy Fest
```

| Failed Years | 
|---| 
```
Rental year: 2023 < Release year: 2024
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | videoclub | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 21 | 314 | 6.69% |
| Multiplicities Errors | 23 | 57 | 40.35% |
| Invariants Errors | 0 | 3 | 0.00% |

| Syntax Errors | 
|---| 
```
Error: An object with name `client1' already exists.
```
```
Error: An object with name `client2' already exists.
```
```
Error: An object with name `client3' already exists.
```
```
Error: An object with name `client25' already exists.
```
```
Error: An object with name `rental1' already exists.
```
```
Error: An object with name `rental2' already exists.
```
```
Error: An object with name `rental3' already exists.
```
```
Error: An object with name `rental30' already exists.
```
```
Error: An object with name `movie1' already exists.
```
```
Error: An object with name `movie2' already exists.
```
```
Error: An object with name `movie3' already exists.
```
```
Error: An object with name `series1' already exists.
```
```
Error: An object with name `series2' already exists.
```
```
Error: An object with name `actor1' already exists.
```
```
Error: An object with name `actor2' already exists.
```
```
Error: An object with name `actor3' already exists.
```
```
Error: An object with name `actor15' already exists.
```
```
Error: Link `ClientRental' between (client1,rental1) already exist.
```
```
Error: Link `ClientRental' between (client2,rental2) already exist.
```
```
Error: Link `ClientRental' between (client3,rental3) already exist.
```
```
Error: Link `RentalCassette' between (rental1,movie1) already exist.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental26' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental27' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental28' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental29' of class `Rental' is connected to 0 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental20' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental21' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental22' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental23' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental24' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental25' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental26' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental27' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental28' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental29' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental11' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental12' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental13' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental14' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental15' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental16' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental17' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental18' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental19' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```

| Videoclub | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Titles | 4 | 11 | 36.36% |
| Types (out of valid Titles) | 4 | 7 | 57.14% |
| Genres (out of valid Titles) | 2 | 4 | 50.00% |
| Actors (out of valid Titles) | 9 | 9 | 100.00% |
| Release year > Rental year (out of valid Titles) | 1 | 7 | 14.29% |

| Failed Titles | 
|---| 
```
Mystery Chronicles
```
```
Dramatic Turns
```
```
Unfolding Tales
```
```
Blockbuster Action
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```
```
Parsed type: movie != API type: series
```
```
Parsed type: movie != API type: series
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Documentary, Short]
```
```
Parsed genre: Action != API genre: [Comedy]
```

| Failed Actors | 
|---| 
```
Tom Steel for movie: Untold Stories
```
```
Gary Bold for movie: Great Adventures
```
```
John Legend for movie: Epic Saga
```
```
Emma Quest for movie: Epic Saga
```
```
Chris Breeze for movie: Action Thriller
```
```
Chris Breeze for movie: Laugh Out Loud
```
```
John Legend for movie: Laugh Out Loud
```
```
Matt Hero for movie: Epic Adventures
```
```
Lara Fame for movie: Comedy Fest
```

| Failed Years | 
|---| 
```
Rental year: 2023 < Release year: 2024
```

