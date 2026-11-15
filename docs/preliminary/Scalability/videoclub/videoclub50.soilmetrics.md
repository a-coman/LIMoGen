# Generation 1
```
-- Creating 10 Clients
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
!client6.isSuspended := true

!new Client('client7')
!client7.clientId := 7
!client7.isSuspended := false

!new Client('client8')
!client8.clientId := 8
!client8.isSuspended := true

!new Client('client9')
!client9.clientId := 9
!client9.isSuspended := false

!new Client('client10')
!client10.clientId := 10
!client10.isSuspended := true

-- Creating 10 Rentals
!new Rental('rental1')
!rental1.date := Date('2023-01-01')

!new Rental('rental2')
!rental2.date := Date('2023-01-02')

!new Rental('rental3')
!rental3.date := Date('2023-01-03')

!new Rental('rental4')
!rental4.date := Date('2023-01-04')

!new Rental('rental5')
!rental5.date := Date('2023-01-05')

!new Rental('rental6')
!rental6.date := Date('2023-01-06')

!new Rental('rental7')
!rental7.date := Date('2023-01-07')

!new Rental('rental8')
!rental8.date := Date('2023-01-08')

!new Rental('rental9')
!rental9.date := Date('2023-01-09')

!new Rental('rental10')
!rental10.date := Date('2023-01-10')

-- Creating 10 Cassettes (Movies and Series)
!new Movie('movie1')
!movie1.title := 'Action Movie 1'
!movie1.availableCopies := 5
!movie1.genre := #Action

!new Movie('movie2')
!movie2.title := 'Comedy Movie 2'
!movie2.availableCopies := 3
!movie2.genre := #Comedy

!new Series('series1')
!series1.title := 'Series 1'
!series1.availableCopies := 2
!series1.episode := 1

!new Series('series2')
!series2.title := 'Series 2'
!series2.availableCopies := 4
!series2.episode := 2

!new Movie('movie3')
!movie3.title := 'Action Movie 3'
!movie3.availableCopies := 6
!movie3.genre := #Action

!new Series('series3')
!series3.title := 'Series 3'
!series3.availableCopies := 1
!series3.episode := 3

!new Movie('movie4')
!movie4.title := 'Comedy Movie 4'
!movie4.availableCopies := 5
!movie4.genre := #Comedy

!new Series('series4')
!series4.title := 'Series 4'
!series4.availableCopies := 2
!series4.episode := 4

!new Movie('movie5')
!movie5.title := 'Action Movie 5'
!movie5.availableCopies := 3
!movie5.genre := #Action

!new Series('series5')
!series5.title := 'Series 5'
!series5.availableCopies := 4
!series5.episode := 5

-- Creating 10 Actors
!new Actor('actor1')
!actor1.name := 'Actor One'

!new Actor('actor2')
!actor2.name := 'Actor Two'

!new Actor('actor3')
!actor3.name := 'Actor Three'

!new Actor('actor4')
!actor4.name := 'Actor Four'

!new Actor('actor5')
!actor5.name := 'Actor Five'

!new Actor('actor6')
!actor6.name := 'Actor Six'

!new Actor('actor7')
!actor7.name := 'Actor Seven'

!new Actor('actor8')
!actor8.name := 'Actor Eight'

!new Actor('actor9')
!actor9.name := 'Actor Nine'

!new Actor('actor10')
!actor10.name := 'Actor Ten'

-- Creating Associations for Clients
!insert (client1, rental1) into ClientRental
!insert (client1, rental2) into ClientRental
!insert (client2, rental3) into ClientRental
!insert (client2, rental4) into ClientRental
!insert (client3, rental5) into ClientRental
!insert (client3, rental6) into ClientRental
!insert (client4, rental7) into ClientRental
!insert (client4, rental8) into ClientRental
!insert (client5, rental9) into ClientRental
!insert (client5, rental10) into ClientRental

-- Creating Associations for Rentals and Cassettes
!insert (rental1, movie1) into RentalCassette
!insert (rental1, series1) into RentalCassette
!insert (rental2, movie2) into RentalCassette
!insert (rental2, series2) into RentalCassette
!insert (rental3, movie3) into RentalCassette
!insert (rental3, series3) into RentalCassette
!insert (rental4, movie4) into RentalCassette
!insert (rental4, series4) into RentalCassette
!insert (rental5, movie5) into RentalCassette
!insert (rental5, series5) into RentalCassette

-- Creating Associations for Cassettes and Actors
!insert (movie1, actor1) into CassetteActor
!insert (movie1, actor2) into CassetteActor
!insert (series1, actor3) into CassetteActor
!insert (series1, actor4) into CassetteActor
!insert (movie2, actor5) into CassetteActor
!insert (series2, actor6) into CassetteActor
!insert (movie3, actor7) into CassetteActor
!insert (series3, actor8) into CassetteActor
!insert (movie4, actor9) into CassetteActor
!insert (series4, actor10) into CassetteActor
-- Creating 3 more Clients
!new Client('client11')
!client11.clientId := 11
!client11.isSuspended := false

!new Client('client12')
!client12.clientId := 12
!client12.isSuspended := true

!new Client('client13')
!client13.clientId := 13
!client13.isSuspended := false

-- Creating 2 more Rentals
!new Rental('rental11')
!rental11.date := Date('2023-01-11')

!new Rental('rental12')
!rental12.date := Date('2023-01-12')

-- Creating 2 more Movies
!new Movie('movie6')
!movie6.title := 'Comedy Movie 6'
!movie6.availableCopies := 4
!movie6.genre := #Comedy

!new Movie('movie7')
!movie7.title := 'Action Movie 7'
!movie7.availableCopies := 2
!movie7.genre := #Action

-- Creating 3 more Actors
!new Actor('actor11')
!actor11.name := 'Actor Eleven'

!new Actor('actor12')
!actor12.name := 'Actor Twelve'

!new Actor('actor13')
!actor13.name := 'Actor Thirteen'

-- Creating Associations for New Clients
!insert (client11, rental11) into ClientRental
!insert (client12, rental11) into ClientRental
!insert (client13, rental12) into ClientRental

-- Creating Associations for New Rentals and Cassettes
!insert (rental11, movie6) into RentalCassette
!insert (rental12, movie7) into RentalCassette

-- Creating Associations for New Cassettes and Actors
!insert (movie6, actor11) into CassetteActor
!insert (movie6, actor12) into CassetteActor
!insert (movie7, actor13) into CassetteActor
```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 175 | 0.00% |
| Multiplicities Errors | 8 | 38 | 21.05% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CassetteActor':
  Object `series5' of class `Series' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `CassetteActor':
  Object `movie5' of class `Movie' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental11' of class `Rental' is connected to 2 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental8' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental9' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental10' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental6' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental7' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```

| Videoclub | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Titles | 6 | 12 | 50.00% |
| Types (out of valid Titles) | 5 | 6 | 83.33% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 6 | 6 | 100.00% |
| Release year > Rental year (out of valid Titles) | 0 | 6 | 0.00% |

| Failed Titles | 
|---| 
```
Comedy Movie 2
```
```
Action Movie 1
```
```
Action Movie 7
```
```
Comedy Movie 6
```
```
Action Movie 5
```
```
Comedy Movie 4
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
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Actor Seven for movie: Action Movie 3
```
```
Actor Ten for movie: Series 4
```
```
Actor Eight for movie: Series 3
```
```
Actor Six for movie: Series 2
```
```
Actor Three for movie: Series 1
```
```
Actor Four for movie: Series 1
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
| Syntax Errors | 0 | 175 | 0.00% |
| Multiplicities Errors | 8 | 38 | 21.05% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CassetteActor':
  Object `series5' of class `Series' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `CassetteActor':
  Object `movie5' of class `Movie' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `ClientRental':
  Object `rental11' of class `Rental' is connected to 2 objects of class `Client'
  at association end `assigned' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental8' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental9' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental10' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental6' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```
```
Multiplicity constraint violation in association `RentalCassette':
  Object `rental7' of class `Rental' is connected to 0 objects of class `Cassette'
  at association end `borrows' but the multiplicity is specified as `1..*'.
```

| Videoclub | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Titles | 6 | 12 | 50.00% |
| Types (out of valid Titles) | 5 | 6 | 83.33% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 6 | 6 | 100.00% |
| Release year > Rental year (out of valid Titles) | 0 | 6 | 0.00% |

| Failed Titles | 
|---| 
```
Comedy Movie 2
```
```
Action Movie 1
```
```
Action Movie 7
```
```
Comedy Movie 6
```
```
Action Movie 5
```
```
Comedy Movie 4
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
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Actor Seven for movie: Action Movie 3
```
```
Actor Ten for movie: Series 4
```
```
Actor Eight for movie: Series 3
```
```
Actor Six for movie: Series 2
```
```
Actor Three for movie: Series 1
```
```
Actor Four for movie: Series 1
```

