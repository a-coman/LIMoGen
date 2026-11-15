# Generation 1
```
!new Client('client1')
!client1.clientId := 1
!client1.isSuspended := false

!new Client('client2')
!client2.clientId := 2
!client2.isSuspended := true

!new Rental('rental1')
!rental1.date := Date('2023-10-10')

!new Rental('rental2')
!rental2.date := Date('2023-10-11')

!new Movie('movie1')
!movie1.title := 'Action Movie'
!movie1.availableCopies := 5
!movie1.genre := #Action

!new Movie('movie2')
!movie2.title := 'Comedy Movie'
!movie2.availableCopies := 3
!movie2.genre := #Comedy

!new Series('series1')
!series1.title := 'Best Series Ever'
!series1.availableCopies := 10
!series1.episode := 1

!new Actor('actor1')
!actor1.name := 'Famous Actor'

!new Actor('actor2')
!actor2.name := 'New Actor'

!insert (client1, rental1) into ClientRental
!insert (client1, rental2) into ClientRental
!insert (rental1, movie1) into RentalCassette
!insert (rental2, movie1) into RentalCassette
!insert (rental2, series1) into RentalCassette
!insert (movie1, actor1) into CassetteActor
!insert (movie1, actor2) into CassetteActor
!insert (series1, actor1) into CassetteActor

-- Covering edge cases

!new Client('client3')
!client3.clientId := 3
!client3.isSuspended := false

!new Rental('rental3')
!rental3.date := Date('2023-10-12')

!new Movie('movie3')
!movie3.title := 'Zero Copies'
!movie3.availableCopies := 0
!movie3.genre := #Action

!new Series('series2')
!series2.title := 'One Episode Wonder'
!series2.availableCopies := 1
!series2.episode := 1

!new Actor('actor3')
!actor3.name := 'Solo Actor'

!insert (client3, rental3) into ClientRental
!insert (rental3, movie3) into RentalCassette
!insert (rental3, series2) into RentalCassette
!insert (movie3, actor3) into CassetteActor
!insert (series2, actor3) into CassetteActor
```
## Generation 1 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CassetteActor':
  Object `movie2' of class `Movie' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 5 | 40.00% |
| Types (out of valid Titles) | 2 | 2 | 100.00% |
| Genres (out of valid Titles) | 2 | 2 | 100.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Zero Copies
```
```
One Episode Wonder
```
```
Best Series Ever
```

| Failed Actors | 
|---| 
```
Famous Actor for movie: Action Movie
```
```
New Actor for movie: Action Movie
```

# Generation 2
```
!new Client('client4')
!client4.clientId := 4
!client4.isSuspended := false

!new Rental('rental4')
!rental4.date := Date('2023-10-13')

!new Movie('movie4')
!movie4.title := 'Thriller Night'
!movie4.availableCopies := 2
!movie4.genre := #Action

!new Series('series3')
!series3.title := 'Comedy Series'
!series3.availableCopies := 3
!series3.episode := 2

!new Actor('actor4')
!actor4.name := 'Legendary Actor'

!new Actor('actor5')
!actor5.name := 'Comic Actor'

!insert (client4, rental4) into ClientRental
!insert (rental4, movie4) into RentalCassette
!insert (rental4, series3) into RentalCassette
!insert (movie4, actor4) into CassetteActor
!insert (series3, actor4) into CassetteActor
!insert (series3, actor5) into CassetteActor
```
## Generation 2 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 2 | 2 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Animation, Short, Comedy]
```

| Failed Actors | 
|---| 
```
Legendary Actor for movie: Comedy Series
```
```
Comic Actor for movie: Comedy Series
```
```
Legendary Actor for movie: Thriller Night
```

# Generation 3
```
!new Client('client5')
!client5.clientId := 5
!client5.isSuspended := true

!new Rental('rental5')
!rental5.date := Date('2023-10-14')

!new Movie('movie5')
!movie5.title := 'Classic Comedy'
!movie5.availableCopies := 4
!movie5.genre := #Comedy

!new Series('series4')
!series4.title := 'Drama Chronicles'
!series4.availableCopies := 8
!series4.episode := 3

!new Actor('actor6')
!actor6.name := 'Dramatic Actor'

!new Actor('actor7')
!actor7.name := 'Comedian Legend'

!insert (client5, rental5) into ClientRental
!insert (rental5, movie5) into RentalCassette
!insert (rental5, series4) into RentalCassette
!insert (movie5, actor7) into CassetteActor
!insert (series4, actor6) into CassetteActor
!insert (series4, actor7) into CassetteActor
```
## Generation 3 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 1 | 1 | 100.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Drama Chronicles
```

| Failed Actors | 
|---| 
```
Comedian Legend for movie: Classic Comedy
```

# Generation 4
```
!new Client('client6')
!client6.clientId := 6
!client6.isSuspended := false

!new Rental('rental6')
!rental6.date := Date('2023-10-15')

!new Movie('movie6')
!movie6.title := 'Sci-Fi Adventure'
!movie6.availableCopies := 6
!movie6.genre := #Action

!new Series('series5')
!series5.title := 'Mysterious Tales'
!series5.availableCopies := 5
!series5.episode := 2

!new Actor('actor8')
!actor8.name := 'Mysterious Actor'

!new Actor('actor9')
!actor9.name := 'Adventure Hero'

!insert (client6, rental6) into ClientRental
!insert (rental6, movie6) into RentalCassette
!insert (rental6, series5) into RentalCassette
!insert (movie6, actor9) into CassetteActor
!insert (series5, actor8) into CassetteActor
!insert (series5, actor9) into CassetteActor
```
## Generation 4 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 0 | 1 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Sci-Fi Adventure
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Mysterious Actor for movie: Mysterious Tales
```
```
Adventure Hero for movie: Mysterious Tales
```

# Generation 5
```
!new Client('client7')
!client7.clientId := 7
!client7.isSuspended := true

!new Rental('rental7')
!rental7.date := Date('2023-10-16')

!new Movie('movie7')
!movie7.title := 'Historical Drama'
!movie7.availableCopies := 1
!movie7.genre := #Comedy

!new Series('series6')
!series6.title := 'Epic Voyage'
!series6.availableCopies := 7
!series6.episode := 5

!new Actor('actor10')
!actor10.name := 'Epic Actor'

!new Actor('actor11')
!actor11.name := 'Historic Figure'

!insert (client7, rental7) into ClientRental
!insert (rental7, movie7) into RentalCassette
!insert (rental7, series6) into RentalCassette
!insert (movie7, actor11) into CassetteActor
!insert (series6, actor10) into CassetteActor
```
## Generation 5 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 1 | 2 | 50.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Genres | 
|---| 
```
Parsed genre: Comedy != API genre: [Drama, History]
```

| Failed Actors | 
|---| 
```
Epic Actor for movie: Epic Voyage
```
```
Historic Figure for movie: Historical Drama
```

# Generation 6
```
!new Client('client8')
!client8.clientId := 8
!client8.isSuspended := false

!new Rental('rental8')
!rental8.date := Date('2023-10-17')

!new Movie('movie8')
!movie8.title := 'Animated Fun'
!movie8.availableCopies := 2
!movie8.genre := #Comedy

!new Series('series7')
!series7.title := 'Sci-Fi Saga'
!series7.availableCopies := 4
!series7.episode := 10

!new Actor('actor12')
!actor12.name := 'Voice Actor One'

!new Actor('actor13')
!actor13.name := 'Voice Actor Two'

!insert (client8, rental8) into ClientRental
!insert (rental8, movie8) into RentalCassette
!insert (rental8, series7) into RentalCassette
!insert (movie8, actor12) into CassetteActor
!insert (series7, actor12) into CassetteActor
!insert (series7, actor13) into CassetteActor
```
## Generation 6 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 0 | 2 | 0.00% |
| Types (out of valid Titles) | 0 | 0 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 0 | 0.00% |
| Release year > Rental year (out of valid Titles) | 0 | 0 | 0.00% |

| Failed Titles | 
|---| 
```
Animated Fun
```
```
Sci-Fi Saga
```

# Generation 7
```
!new Client('client9')
!client9.clientId := 9
!client9.isSuspended := true

!new Rental('rental9')
!rental9.date := Date('2023-10-18')

!new Movie('movie9')
!movie9.title := 'Thrilling Mystery'
!movie9.availableCopies := 4
!movie9.genre := #Action

!new Series('series8')
!series8.title := 'Fantasy Journey'
!series8.availableCopies := 6
!series8.episode := 7

!new Actor('actor14')
!actor14.name := 'Thriller Specialist'

!new Actor('actor15')
!actor15.name := 'Fantasy Star'

!insert (client9, rental9) into ClientRental
!insert (rental9, movie9) into RentalCassette
!insert (rental9, series8) into RentalCassette
!insert (movie9, actor14) into CassetteActor
!insert (series8, actor14) into CassetteActor
!insert (series8, actor15) into CassetteActor
```
## Generation 7 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 0 | 2 | 0.00% |
| Types (out of valid Titles) | 0 | 0 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 0 | 0.00% |
| Release year > Rental year (out of valid Titles) | 0 | 0 | 0.00% |

| Failed Titles | 
|---| 
```
Thrilling Mystery
```
```
Fantasy Journey
```

# Generation 8
```
!new Client('client10')
!client10.clientId := 10
!client10.isSuspended := false

!new Rental('rental10')
!rental10.date := Date('2023-10-19')

!new Movie('movie10')
!movie10.title := 'Romantic Escape'
!movie10.availableCopies := 3
!movie10.genre := #Comedy

!new Series('series9')
!series9.title := 'Dark Legends'
!series9.availableCopies := 9
!series9.episode := 4

!new Actor('actor16')
!actor16.name := 'Romantic Lead'

!new Actor('actor17')
!actor17.name := 'Dark Villain'

!insert (client10, rental10) into ClientRental
!insert (rental10, movie10) into RentalCassette
!insert (rental10, series9) into RentalCassette
!insert (movie10, actor16) into CassetteActor
!insert (series9, actor17) into CassetteActor
!insert (series9, actor16) into CassetteActor
```
## Generation 8 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 0 | 1 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Romantic Escape
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Dark Villain for movie: Dark Legends
```
```
Romantic Lead for movie: Dark Legends
```

# Generation 9
```
!new Client('client11')
!client11.clientId := 11
!client11.isSuspended := false

!new Rental('rental11')
!rental11.date := Date('2023-10-20')

!new Movie('movie11')
!movie11.title := 'Adventure Chronicles'
!movie11.availableCopies := 5
!movie11.genre := #Action

!new Series('series10')
!series10.title := 'Comedy Hour'
!series10.availableCopies := 8
!series10.episode := 3

!new Actor('actor18')
!actor18.name := 'Adventure Protagonist'

!new Actor('actor19')
!actor19.name := 'Funny Sidekick'

!insert (client11, rental11) into ClientRental
!insert (rental11, movie11) into RentalCassette
!insert (rental11, series10) into RentalCassette
!insert (movie11, actor18) into CassetteActor
!insert (series10, actor19) into CassetteActor
!insert (series10, actor18) into CassetteActor
```
## Generation 9 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Adventure Chronicles
```

| Failed Actors | 
|---| 
```
Funny Sidekick for movie: Comedy Hour
```
```
Adventure Protagonist for movie: Comedy Hour
```

# Generation 10
```
!new Client('client12')
!client12.clientId := 12
!client12.isSuspended := true

!new Rental('rental12')
!rental12.date := Date('2023-10-21')

!new Movie('movie12')
!movie12.title := 'Future Vision'
!movie12.availableCopies := 7
!movie12.genre := #Action

!new Series('series11')
!series11.title := 'Laugh Riot'
!series11.availableCopies := 2
!series11.episode := 6

!new Actor('actor20')
!actor20.name := 'Sci-Fi Lead'

!new Actor('actor21')
!actor21.name := 'Comedy Genius'

!insert (client12, rental12) into ClientRental
!insert (rental12, movie12) into RentalCassette
!insert (rental12, series11) into RentalCassette
!insert (movie12, actor20) into CassetteActor
!insert (series11, actor21) into CassetteActor
!insert (series11, actor20) into CassetteActor
```
## Generation 10 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Laugh Riot
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Short, Comedy, Sci-Fi]
```

| Failed Actors | 
|---| 
```
Sci-Fi Lead for movie: Future Vision
```

# Generation 11
```
!new Client('client13')
!client13.clientId := 13
!client13.isSuspended := false

!new Rental('rental13')
!rental13.date := Date('2023-10-22')

!new Movie('movie13')
!movie13.title := 'Mystery Adventure'
!movie13.availableCopies := 3
!movie13.genre := #Action

!new Series('series12')
!series12.title := 'Comedy Nights'
!series12.availableCopies := 4
!series12.episode := 8

!new Actor('actor22')
!actor22.name := 'Detective Lead'

!new Actor('actor23')
!actor23.name := 'Laugh Master'

!insert (client13, rental13) into ClientRental
!insert (rental13, movie13) into RentalCassette
!insert (rental13, series12) into RentalCassette
!insert (movie13, actor22) into CassetteActor
!insert (series12, actor23) into CassetteActor
!insert (series12, actor22) into CassetteActor
```
## Generation 11 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 2 | 2 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Adventure, Mystery]
```

| Failed Actors | 
|---| 
```
Detective Lead for movie: Mystery Adventure
```
```
Laugh Master for movie: Comedy Nights
```
```
Detective Lead for movie: Comedy Nights
```

# Generation 12
```
!new Client('client14')
!client14.clientId := 14
!client14.isSuspended := true

!new Rental('rental14')
!rental14.date := Date('2023-10-23')

!new Movie('movie14')
!movie14.title := 'Epic Journey'
!movie14.availableCopies := 5
!movie14.genre := #Action

!new Series('series13')
!series13.title := 'Sitcom Chronicles'
!series13.availableCopies := 6
!series13.episode := 11

!new Actor('actor24')
!actor24.name := 'Epic Hero'

!new Actor('actor25')
!actor25.name := 'Sitcom Star'

!insert (client14, rental14) into ClientRental
!insert (rental14, movie14) into RentalCassette
!insert (rental14, series13) into RentalCassette
!insert (movie14, actor24) into CassetteActor
!insert (series13, actor25) into CassetteActor
!insert (series13, actor24) into CassetteActor
```
## Generation 12 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Sitcom Chronicles
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Documentary]
```

| Failed Actors | 
|---| 
```
Epic Hero for movie: Epic Journey
```

# Generation 13
```
!new Client('client15')
!client15.clientId := 15
!client15.isSuspended := false

!new Rental('rental15')
!rental15.date := Date('2023-10-24')

!new Movie('movie15')
!movie15.title := 'Silent Drama'
!movie15.availableCopies := 0
!movie15.genre := #Comedy

!new Series('series14')
!series14.title := 'Historical Epic'
!series14.availableCopies := 10
!series14.episode := 9

!new Actor('actor26')
!actor26.name := 'Silent Star'

!new Actor('actor27')
!actor27.name := 'Historical Icon'

!insert (client15, rental15) into ClientRental
!insert (rental15, movie15) into RentalCassette
!insert (rental15, series14) into RentalCassette
!insert (movie15, actor26) into CassetteActor
!insert (series14, actor27) into CassetteActor
!insert (series14, actor26) into CassetteActor
```
## Generation 13 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 0 | 2 | 0.00% |
| Types (out of valid Titles) | 0 | 0 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 0 | 0.00% |
| Release year > Rental year (out of valid Titles) | 0 | 0 | 0.00% |

| Failed Titles | 
|---| 
```
Silent Drama
```
```
Historical Epic
```

# Generation 14
```
!new Client('client16')
!client16.clientId := 16
!client16.isSuspended := false

!new Rental('rental16')
!rental16.date := Date('2023-10-25')

!new Movie('movie16')
!movie16.title := 'Comedy of Errors'
!movie16.availableCopies := 6
!movie16.genre := #Comedy

!new Series('series15')
!series15.title := 'Uncharted Depths'
!series15.availableCopies := 7
!series15.episode := 12

!new Actor('actor28')
!actor28.name := 'Comedy King'

!new Actor('actor29')
!actor29.name := 'Depth Explorer'

!insert (client16, rental16) into ClientRental
!insert (rental16, movie16) into RentalCassette
!insert (rental16, series15) into RentalCassette
!insert (movie16, actor28) into CassetteActor
!insert (series15, actor29) into CassetteActor
!insert (series15, actor28) into CassetteActor
```
## Generation 14 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 1 | 1 | 100.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Uncharted Depths
```

| Failed Actors | 
|---| 
```
Comedy King for movie: Comedy of Errors
```

# Generation 15
```
!new Client('client17')
!client17.clientId := 17
!client17.isSuspended := true

!new Rental('rental17')
!rental17.date := Date('2023-10-26')

!new Movie('movie17')
!movie17.title := 'Mystic Realms'
!movie17.availableCopies := 1
!movie17.genre := #Action

!new Series('series16')
!series16.title := 'Laugh Factory'
!series16.availableCopies := 3
!series16.episode := 5

!new Actor('actor30')
!actor30.name := 'Mystic Adventurer'

!new Actor('actor31')
!actor31.name := 'Comedy Legend'

!insert (client17, rental17) into ClientRental
!insert (rental17, movie17) into RentalCassette
!insert (rental17, series16) into RentalCassette
!insert (movie17, actor30) into CassetteActor
!insert (series16, actor31) into CassetteActor
!insert (series16, actor30) into CassetteActor
```
## Generation 15 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Mystic Realms
```

| Failed Actors | 
|---| 
```
Comedy Legend for movie: Laugh Factory
```
```
Mystic Adventurer for movie: Laugh Factory
```

# Generation 16
```
!new Client('client18')
!client18.clientId := 18
!client18.isSuspended := false

!new Rental('rental18')
!rental18.date := Date('2023-10-27')

!new Movie('movie18')
!movie18.title := 'Space Odyssey'
!movie18.availableCopies := 4
!movie18.genre := #Action

!new Series('series17')
!series17.title := 'Daily Laughs'
!series17.availableCopies := 5
!series17.episode := 2

!new Actor('actor32')
!actor32.name := 'Galactic Explorer'

!new Actor('actor33')
!actor33.name := 'Humor Pioneer'

!insert (client18, rental18) into ClientRental
!insert (rental18, movie18) into RentalCassette
!insert (rental18, series17) into RentalCassette
!insert (movie18, actor32) into CassetteActor
!insert (series17, actor33) into CassetteActor
!insert (series17, actor32) into CassetteActor
```
## Generation 16 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Daily Laughs
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Adventure, Sci-Fi]
```

| Failed Actors | 
|---| 
```
Galactic Explorer for movie: Space Odyssey
```

# Generation 17
```
!new Client('client19')
!client19.clientId := 19
!client19.isSuspended := true

!new Rental('rental19')
!rental19.date := Date('2023-10-28')

!new Movie('movie19')
!movie19.title := 'Fantasy Quest'
!movie19.availableCopies := 2
!movie19.genre := #Action

!new Series('series18')
!series18.title := 'Stand-Up Specials'
!series18.availableCopies := 6
!series18.episode := 1

!new Actor('actor34')
!actor34.name := 'Fantasy Hero'

!new Actor('actor35')
!actor35.name := 'Stand-Up Star'

!insert (client19, rental19) into ClientRental
!insert (rental19, movie19) into RentalCassette
!insert (rental19, series18) into RentalCassette
!insert (movie19, actor34) into CassetteActor
!insert (series18, actor35) into CassetteActor
!insert (series18, actor34) into CassetteActor
```
## Generation 17 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Fantasy Quest
```

| Failed Actors | 
|---| 
```
Stand-Up Star for movie: Stand-Up Specials
```
```
Fantasy Hero for movie: Stand-Up Specials
```

# Generation 18
```
!new Client('client20')
!client20.clientId := 20
!client20.isSuspended := false

!new Rental('rental20')
!rental20.date := Date('2023-10-29')

!new Movie('movie20')
!movie20.title := 'Cyber Journey'
!movie20.availableCopies := 5
!movie20.genre := #Action

!new Series('series19')
!series19.title := 'Sketch Comedy'
!series19.availableCopies := 4
!series19.episode := 15

!new Actor('actor36')
!actor36.name := 'Cyber Warrior'

!new Actor('actor37')
!actor37.name := 'Sketch Artist'

!insert (client20, rental20) into ClientRental
!insert (rental20, movie20) into RentalCassette
!insert (rental20, series19) into RentalCassette
!insert (movie20, actor36) into CassetteActor
!insert (series19, actor37) into CassetteActor
!insert (series19, actor36) into CassetteActor
```
## Generation 18 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 0 | 1 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Cyber Journey
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Sketch Artist for movie: Sketch Comedy
```
```
Cyber Warrior for movie: Sketch Comedy
```

# Generation 19
```
!new Client('client21')
!client21.clientId := 21
!client21.isSuspended := false

!new Rental('rental21')
!rental21.date := Date('2023-10-30')

!new Movie('movie21')
!movie21.title := 'Island Adventure'
!movie21.availableCopies := 3
!movie21.genre := #Action

!new Series('series20')
!series20.title := 'Late Night Laughs'
!series20.availableCopies := 7
!series20.episode := 3

!new Actor('actor38')
!actor38.name := 'Island Survivor'

!new Actor('actor39')
!actor39.name := 'Night Show Comedian'

!insert (client21, rental21) into ClientRental
!insert (rental21, movie21) into RentalCassette
!insert (rental21, series20) into RentalCassette
!insert (movie21, actor38) into CassetteActor
!insert (series20, actor39) into CassetteActor
!insert (series20, actor38) into CassetteActor
```
## Generation 19 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Late Night Laughs
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Documentary, Short]
```

| Failed Actors | 
|---| 
```
Island Survivor for movie: Island Adventure
```

# Generation 20
```
!new Client('client22')
!client22.clientId := 22
!client22.isSuspended := true

!new Rental('rental22')
!rental22.date := Date('2023-10-31')

!new Movie('movie22')
!movie22.title := 'Gothic Mystery'
!movie22.availableCopies := 4
!movie22.genre := #Comedy

!new Series('series21')
!series21.title := 'Reality Adventures'
!series21.availableCopies := 9
!series21.episode := 7

!new Actor('actor40')
!actor40.name := 'Gothic Star'

!new Actor('actor41')
!actor41.name := 'Reality Show Host'

!insert (client22, rental22) into ClientRental
!insert (rental22, movie22) into RentalCassette
!insert (rental22, series21) into RentalCassette
!insert (movie22, actor40) into CassetteActor
!insert (series21, actor41) into CassetteActor
!insert (series21, actor40) into CassetteActor
```
## Generation 20 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 0 | 1 | 0.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Reality Adventures
```

| Failed Types | 
|---| 
```
Parsed type: movie != API type: series
```

| Failed Genres | 
|---| 
```
Parsed genre: Comedy != API genre: [Horror]
```

| Failed Actors | 
|---| 
```
Gothic Star for movie: Gothic Mystery
```

# Generation 21
```
!new Client('client23')
!client23.clientId := 23
!client23.isSuspended := false

!new Rental('rental23')
!rental23.date := Date('2023-11-01')

!new Movie('movie23')
!movie23.title := 'Urban Legends'
!movie23.availableCopies := 8
!movie23.genre := #Action

!new Series('series22')
!series22.title := 'Animated Tales'
!series22.availableCopies := 2
!series22.episode := 4

!new Actor('actor42')
!actor42.name := 'Urban Myth Buster'

!new Actor('actor43')
!actor43.name := 'Voiceover Artist'

!insert (client23, rental23) into ClientRental
!insert (rental23, movie23) into RentalCassette
!insert (rental23, series22) into RentalCassette
!insert (movie23, actor42) into CassetteActor
!insert (series22, actor43) into CassetteActor
!insert (series22, actor42) into CassetteActor
```
## Generation 21 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 1 | 2 | 50.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Types | 
|---| 
```
Parsed type: movie != API type: series
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Crime, Fantasy, History]
```

| Failed Actors | 
|---| 
```
Urban Myth Buster for movie: Urban Legends
```
```
Voiceover Artist for movie: Animated Tales
```
```
Urban Myth Buster for movie: Animated Tales
```

# Generation 22
```
!new Client('client24')
!client24.clientId := 24
!client24.isSuspended := true

!new Rental('rental24')
!rental24.date := Date('2023-11-02')

!new Movie('movie24')
!movie24.title := 'Quantum Leap'
!movie24.availableCopies := 0
!movie24.genre := #Action

!new Series('series23')
!series23.title := 'Cooking Showdown'
!series23.availableCopies := 5
!series23.episode := 1

!new Actor('actor44')
!actor44.name := 'Time Traveler'

!new Actor('actor45')
!actor45.name := 'Master Chef'

!insert (client24, rental24) into ClientRental
!insert (rental24, movie24) into RentalCassette
!insert (rental24, series23) into RentalCassette
!insert (movie24, actor44) into CassetteActor
!insert (series23, actor45) into CassetteActor
!insert (series23, actor44) into CassetteActor
```
## Generation 22 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 1 | 2 | 50.00% |
| Genres (out of valid Titles) | 1 | 1 | 100.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Types | 
|---| 
```
Parsed type: movie != API type: series
```

| Failed Actors | 
|---| 
```
Time Traveler for movie: Quantum Leap
```
```
Master Chef for movie: Cooking Showdown
```
```
Time Traveler for movie: Cooking Showdown
```

# Generation 23
```
!new Client('client25')
!client25.clientId := 25
!client25.isSuspended := false

!new Rental('rental25')
!rental25.date := Date('2023-11-03')

!new Movie('movie25')
!movie25.title := 'Virtual Reality'
!movie25.availableCopies := 6
!movie25.genre := #Comedy

!new Series('series24')
!series24.title := 'Myth Busters'
!series24.availableCopies := 3
!series24.episode := 9

!new Actor('actor46')
!actor46.name := 'VR Specialist'

!new Actor('actor47')
!actor47.name := 'Scientific Investigator'

!insert (client25, rental25) into ClientRental
!insert (rental25, movie25) into RentalCassette
!insert (rental25, series24) into RentalCassette
!insert (movie25, actor46) into CassetteActor
!insert (series24, actor47) into CassetteActor
!insert (series24, actor46) into CassetteActor
```
## Generation 23 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Myth Busters
```

| Failed Genres | 
|---| 
```
Parsed genre: Comedy != API genre: [Drama, Thriller, Action]
```

| Failed Actors | 
|---| 
```
VR Specialist for movie: Virtual Reality
```

# Generation 24
```
!new Client('client26')
!client26.clientId := 26
!client26.isSuspended := true

!new Rental('rental26')
!rental26.date := Date('2023-11-04')

!new Movie('movie26')
!movie26.title := 'Mystery Island'
!movie26.availableCopies := 1
!movie26.genre := #Action

!new Series('series25')
!series25.title := 'Classic Comedies'
!series25.availableCopies := 8
!series25.episode := 10

!new Actor('actor48')
!actor48.name := 'Island Explorer'

!new Actor('actor49')
!actor49.name := 'Vintage Comedian'

!insert (client26, rental26) into ClientRental
!insert (rental26, movie26) into RentalCassette
!insert (rental26, series25) into RentalCassette
!insert (movie26, actor48) into CassetteActor
!insert (series25, actor49) into CassetteActor
!insert (series25, actor48) into CassetteActor
```
## Generation 24 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Classic Comedies
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Mystery]
```

| Failed Actors | 
|---| 
```
Island Explorer for movie: Mystery Island
```

# Generation 25
```
!new Client('client27')
!client27.clientId := 27
!client27.isSuspended := false

!new Rental('rental27')
!rental27.date := Date('2023-11-05')

!new Movie('movie27')
!movie27.title := 'Galactic Battles'
!movie27.availableCopies := 7
!movie27.genre := #Action

!new Series('series26')
!series26.title := 'Daily Sitcom'
!series26.availableCopies := 6
!series26.episode := 12

!new Actor('actor50')
!actor50.name := 'Space Commander'

!new Actor('actor51')
!actor51.name := 'Sitcom Star'

!insert (client27, rental27) into ClientRental
!insert (rental27, movie27) into RentalCassette
!insert (rental27, series26) into RentalCassette
!insert (movie27, actor50) into CassetteActor
!insert (series26, actor51) into CassetteActor
!insert (series26, actor50) into CassetteActor
```
## Generation 25 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Daily Sitcom
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Short, Sci-Fi]
```

| Failed Actors | 
|---| 
```
Space Commander for movie: Galactic Battles
```

# Generation 26
```
!new Client('client28')
!client28.clientId := 28
!client28.isSuspended := true

!new Rental('rental28')
!rental28.date := Date('2023-11-06')

!new Movie('movie28')
!movie28.title := 'Crime Thriller'
!movie28.availableCopies := 5
!movie28.genre := #Action

!new Series('series27')
!series27.title := 'Music Legends'
!series27.availableCopies := 2
!series27.episode := 5

!new Actor('actor52')
!actor52.name := 'Detective Pro'

!new Actor('actor53')
!actor53.name := 'Rock Icon'

!insert (client28, rental28) into ClientRental
!insert (rental28, movie28) into RentalCassette
!insert (rental28, series27) into RentalCassette
!insert (movie28, actor52) into CassetteActor
!insert (series27, actor53) into CassetteActor
!insert (series27, actor52) into CassetteActor
```
## Generation 26 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 2 | 2 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 2 | 50.00% |

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Documentary]
```

| Failed Actors | 
|---| 
```
Rock Icon for movie: Music Legends
```
```
Detective Pro for movie: Music Legends
```
```
Detective Pro for movie: Crime Thriller
```

| Failed Years | 
|---| 
```
Rental year: 2023<Release year: 2024
```

# Generation 27
```
!new Client('client29')
!client29.clientId := 29
!client29.isSuspended := false

!new Rental('rental29')
!rental29.date := Date('2023-11-07')

!new Movie('movie29')
!movie29.title := 'Ancient Secrets'
!movie29.availableCopies := 3
!movie29.genre := #Action

!new Series('series28')
!series28.title := 'Tech Innovations'
!series28.availableCopies := 4
!series28.episode := 14

!new Actor('actor54')
!actor54.name := 'Archaeologist Hero'

!new Actor('actor55')
!actor55.name := 'Tech Guru'

!insert (client29, rental29) into ClientRental
!insert (rental29, movie29) into RentalCassette
!insert (rental29, series28) into RentalCassette
!insert (movie29, actor54) into CassetteActor
!insert (series28, actor55) into CassetteActor
!insert (series28, actor54) into CassetteActor
```
## Generation 27 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 1 | 1 | 100.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 1 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Tech Innovations
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Adult, Fantasy]
```

| Failed Actors | 
|---| 
```
Archaeologist Hero for movie: Ancient Secrets
```

# Generation 28
```
!new Client('client30')
!client30.clientId := 30
!client30.isSuspended := true

!new Rental('rental30')
!rental30.date := Date('2023-11-08')

!new Movie('movie30')
!movie30.title := 'Underwater Odyssey'
!movie30.availableCopies := 2
!movie30.genre := #Action

!new Series('series29')
!series29.title := 'Culinary Delights'
!series29.availableCopies := 9
!series29.episode := 6

!new Actor('actor56')
!actor56.name := 'Marine Biologist'

!new Actor('actor57')
!actor57.name := 'Renowned Chef'

!insert (client30, rental30) into ClientRental
!insert (rental30, movie30) into RentalCassette
!insert (rental30, series29) into RentalCassette
!insert (movie30, actor56) into CassetteActor
!insert (series29, actor57) into CassetteActor
!insert (series29, actor56) into CassetteActor
```
## Generation 28 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 1 | 2 | 50.00% |
| Types (out of valid Titles) | 0 | 1 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 2 | 0.00% |
| Release year > Rental year (out of valid Titles) | 1 | 1 | 100.00% |

| Failed Titles | 
|---| 
```
Underwater Odyssey
```

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Actors | 
|---| 
```
Renowned Chef for movie: Culinary Delights
```
```
Marine Biologist for movie: Culinary Delights
```

# Generation 29
```
!new Client('client31')
!client31.clientId := 31
!client31.isSuspended := false

!new Rental('rental31')
!rental31.date := Date('2023-11-09')

!new Movie('movie31')
!movie31.title := 'Desert Trek'
!movie31.availableCopies := 4
!movie31.genre := #Action

!new Series('series30')
!series30.title := 'Behind the Scenes'
!series30.availableCopies := 3
!series30.episode := 7

!new Actor('actor58')
!actor58.name := 'Explorer Adventurer'

!new Actor('actor59')
!actor59.name := 'Documentary Host'

!insert (client31, rental31) into ClientRental
!insert (rental31, movie31) into RentalCassette
!insert (rental31, series30) into RentalCassette
!insert (movie31, actor58) into CassetteActor
!insert (series30, actor59) into CassetteActor
!insert (series30, actor58) into CassetteActor
```
## Generation 29 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 2 | 2 | 100.00% |
| Types (out of valid Titles) | 1 | 2 | 50.00% |
| Genres (out of valid Titles) | 0 | 1 | 0.00% |
| Actors (out of valid Titles) | 0 | 3 | 0.00% |
| Release year > Rental year (out of valid Titles) | 2 | 2 | 100.00% |

| Failed Types | 
|---| 
```
Parsed type: series != API type: movie
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Comedy]
```

| Failed Actors | 
|---| 
```
Documentary Host for movie: Behind the Scenes
```
```
Explorer Adventurer for movie: Behind the Scenes
```
```
Explorer Adventurer for movie: Desert Trek
```

# Generation 30
```
!new Client('client32')
!client32.clientId := 32
!client32.isSuspended := true

!new Rental('rental32')
!rental32.date := Date('2023-11-10')

!new Movie('movie32')
!movie32.title := 'Canyon Climb'
!movie32.availableCopies := 1
!movie32.genre := #Action

!new Series('series31')
!series31.title := 'Art Expression'
!series31.availableCopies := 8
!series31.episode := 3

!new Actor('actor60')
!actor60.name := 'Climbing Champion'

!new Actor('actor61')
!actor61.name := 'Art Curator'

!insert (client32, rental32) into ClientRental
!insert (rental32, movie32) into RentalCassette
!insert (rental32, series31) into RentalCassette
!insert (movie32, actor60) into CassetteActor
!insert (series31, actor61) into CassetteActor
!insert (series31, actor60) into CassetteActor
```
## Generation 30 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 0 | 2 | 0.00% |
| Types (out of valid Titles) | 0 | 0 | 0.00% |
| Genres (out of valid Titles) | 0 | 0 | 0.00% |
| Actors (out of valid Titles) | 0 | 0 | 0.00% |
| Release year > Rental year (out of valid Titles) | 0 | 0 | 0.00% |

| Failed Titles | 
|---| 
```
Art Expression
```
```
Canyon Climb
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | GPT_4O | 
| Type | Simple | 
| System | videoclub | 
| Number of generations | 30 | 

| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CassetteActor':
  Object `movie2' of class `Movie' is connected to 0 objects of class `Actor'
  at association end `has' but the multiplicity is specified as `1..*'.
```

| Videoclub | Valid | Total | Success (%) | 
|---|---|---|---| 
| Titles | 34 | 63 | 53.97% |
| Types (out of valid Titles) | 25 | 34 | 73.53% |
| Genres (out of valid Titles) | 5 | 20 | 25.00% |
| Actors (out of valid Titles) | 0 | 47 | 0.00% |
| Release year > Rental year (out of valid Titles) | 32 | 33 | 96.97% |

| Failed Titles | 
|---| 
```
Zero Copies
```
```
One Episode Wonder
```
```
Best Series Ever
```
```
Drama Chronicles
```
```
Sci-Fi Adventure
```
```
Animated Fun
```
```
Sci-Fi Saga
```
```
Thrilling Mystery
```
```
Fantasy Journey
```
```
Romantic Escape
```
```
Adventure Chronicles
```
```
Laugh Riot
```
```
Sitcom Chronicles
```
```
Silent Drama
```
```
Historical Epic
```
```
Uncharted Depths
```
```
Mystic Realms
```
```
Daily Laughs
```
```
Fantasy Quest
```
```
Cyber Journey
```
```
Late Night Laughs
```
```
Reality Adventures
```
```
Myth Busters
```
```
Classic Comedies
```
```
Daily Sitcom
```
```
Tech Innovations
```
```
Underwater Odyssey
```
```
Art Expression
```
```
Canyon Climb
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
Parsed type: movie != API type: series
```
```
Parsed type: movie != API type: series
```
```
Parsed type: movie != API type: series
```
```
Parsed type: series != API type: movie
```
```
Parsed type: series != API type: movie
```

| Failed Genres | 
|---| 
```
Parsed genre: Action != API genre: [Animation, Short, Comedy]
```
```
Parsed genre: Comedy != API genre: [Drama, History]
```
```
Parsed genre: Action != API genre: [Short, Comedy, Sci-Fi]
```
```
Parsed genre: Action != API genre: [Adventure, Mystery]
```
```
Parsed genre: Action != API genre: [Documentary]
```
```
Parsed genre: Action != API genre: [Adventure, Sci-Fi]
```
```
Parsed genre: Action != API genre: [Documentary, Short]
```
```
Parsed genre: Comedy != API genre: [Horror]
```
```
Parsed genre: Action != API genre: [Crime, Fantasy, History]
```
```
Parsed genre: Comedy != API genre: [Drama, Thriller, Action]
```
```
Parsed genre: Action != API genre: [Mystery]
```
```
Parsed genre: Action != API genre: [Short, Sci-Fi]
```
```
Parsed genre: Action != API genre: [Documentary]
```
```
Parsed genre: Action != API genre: [Adult, Fantasy]
```
```
Parsed genre: Action != API genre: [Comedy]
```

| Failed Actors | 
|---| 
```
Famous Actor for movie: Action Movie
```
```
New Actor for movie: Action Movie
```
```
Legendary Actor for movie: Comedy Series
```
```
Comic Actor for movie: Comedy Series
```
```
Legendary Actor for movie: Thriller Night
```
```
Comedian Legend for movie: Classic Comedy
```
```
Mysterious Actor for movie: Mysterious Tales
```
```
Adventure Hero for movie: Mysterious Tales
```
```
Epic Actor for movie: Epic Voyage
```
```
Historic Figure for movie: Historical Drama
```
```
Dark Villain for movie: Dark Legends
```
```
Romantic Lead for movie: Dark Legends
```
```
Funny Sidekick for movie: Comedy Hour
```
```
Adventure Protagonist for movie: Comedy Hour
```
```
Sci-Fi Lead for movie: Future Vision
```
```
Detective Lead for movie: Mystery Adventure
```
```
Laugh Master for movie: Comedy Nights
```
```
Detective Lead for movie: Comedy Nights
```
```
Epic Hero for movie: Epic Journey
```
```
Comedy King for movie: Comedy of Errors
```
```
Comedy Legend for movie: Laugh Factory
```
```
Mystic Adventurer for movie: Laugh Factory
```
```
Galactic Explorer for movie: Space Odyssey
```
```
Stand-Up Star for movie: Stand-Up Specials
```
```
Fantasy Hero for movie: Stand-Up Specials
```
```
Sketch Artist for movie: Sketch Comedy
```
```
Cyber Warrior for movie: Sketch Comedy
```
```
Island Survivor for movie: Island Adventure
```
```
Gothic Star for movie: Gothic Mystery
```
```
Urban Myth Buster for movie: Urban Legends
```
```
Voiceover Artist for movie: Animated Tales
```
```
Urban Myth Buster for movie: Animated Tales
```
```
Time Traveler for movie: Quantum Leap
```
```
Master Chef for movie: Cooking Showdown
```
```
Time Traveler for movie: Cooking Showdown
```
```
VR Specialist for movie: Virtual Reality
```
```
Island Explorer for movie: Mystery Island
```
```
Space Commander for movie: Galactic Battles
```
```
Rock Icon for movie: Music Legends
```
```
Detective Pro for movie: Music Legends
```
```
Detective Pro for movie: Crime Thriller
```
```
Archaeologist Hero for movie: Ancient Secrets
```
```
Renowned Chef for movie: Culinary Delights
```
```
Marine Biologist for movie: Culinary Delights
```
```
Documentary Host for movie: Behind the Scenes
```
```
Explorer Adventurer for movie: Behind the Scenes
```
```
Explorer Adventurer for movie: Desert Trek
```

| Failed Years | 
|---| 
```
Rental year: 2023<Release year: 2024
```

