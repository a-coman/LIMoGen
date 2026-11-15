# Generation 1
```
!new Driver('driver1')
!driver1.id := 'D001'
!driver1.name := 'Alice Johnson'

!new Driver('driver2')
!driver2.id := 'D002'
!driver2.name := 'Bob Smith'

!new Shipment('shipment1')
!shipment1.id := 'S001'
!shipment1.status := #NEW

!new Shipment('shipment2')
!shipment2.id := 'S002'
!shipment2.status := #UNDERWAY

!new Address('address1')
!address1.text := '123 Main St, Springfield'

!new Address('address2')
!address2.text := '456 Elm St, Springfield'

!new Address('address3')
!address3.text := '789 Maple St, Shelbyville'

!new GeoLocation('geolocation1')
!geolocation1.latitude := 40.7128
!geolocation1.longitude := -74.0060

!new GeoLocation('geolocation2')
!geolocation2.latitude := 34.0522
!geolocation2.longitude := -118.2437

!new GeoLocation('geolocation3')
!geolocation3.latitude := 37.7749
!geolocation3.longitude := -122.4194

!new Customer('customer1')
!customer1.id := 'C001'
!customer1.name := 'Charlie Brown'
!customer1.twitterUserName := '@charlieB'

!new Customer('customer2')
!customer2.id := 'C002'
!customer2.name := 'Lucy Van Pelt'
!customer2.twitterUserName := '@lucyVP'

!new Station('station1')

!insert (driver1, shipment1) into DriverShipment

!insert (shipment1, address1) into ShipmentContainsPickUpAddress
!insert (shipment1, address2) into ShipmentContainsDeliveryAddress

!insert (address1, geolocation1) into AddressContainsGeoLocation
!insert (address2, geolocation2) into AddressContainsGeoLocation

!insert (customer1, shipment1) into CustomerConsistsOfShipment
!insert (station1, shipment1) into StationShipment

!insert (station1, customer1) into StationContainsCustomer
!insert (station1, driver1) into StationContainsDriver

!new Shipment('shipment3')
!shipment3.id := 'S003'
!shipment3.status := #DELIVERED

!insert (shipment3, address2) into ShipmentContainsPickUpAddress
!insert (shipment3, address3) into ShipmentContainsDeliveryAddress

!insert (address3, geolocation3) into AddressContainsGeoLocation

!insert (driver2, shipment3) into DriverShipment

!insert (customer2, shipment3) into CustomerConsistsOfShipment
!insert (station1, shipment3) into StationShipment

!insert (station1, customer2) into StationContainsCustomer
!insert (station1, driver2) into StationContainsDriver
```
## Generation 1 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 4 | 
| Invariants Errors | 1 | 

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```

| Invariants Errors | 
|---| 
```
checking invariant (3) `Shipment::differentPickupAndDeliveryAddress': FAILED.
```

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 2 | 3 | 66.67% |
| Lat/Lon (out of valid addresses) | 0 | 2 | 0.00% |
| Twitter | 2 | 2 | 100.00% |

| Invalid Addresses | 
|---| 
```
789 Maple St, Shelbyville
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: 34.0522 Lon: -118.2437 for address: 456 Elm St, Springfield
```
```
Invalid Lat: 40.7128 Lon: -74.006 for address: 123 Main St, Springfield
```

# Generation 2
```
!new Driver('driver3')
!driver3.id := 'D003'
!driver3.name := 'Emma Stone'

!new Shipment('shipment4')
!shipment4.id := 'S004'
!shipment4.status := #ASSIGNED

!new Address('address4')
!address4.text := '111 Oak St, Metropolis'

!new Address('address5')
!address5.text := '222 Pine St, Gotham'

!new GeoLocation('geolocation4')
!geolocation4.latitude := 51.5074
!geolocation4.longitude := -0.1278

!new GeoLocation('geolocation5')
!geolocation5.latitude := 48.8566
!geolocation5.longitude := 2.3522

!new Customer('customer3')
!customer3.id := 'C003'
!customer3.name := 'Bruce Wayne'
!customer3.twitterUserName := '@bruceW'

!new Station('station2')

!insert (driver3, shipment4) into DriverShipment

!insert (shipment4, address4) into ShipmentContainsPickUpAddress
!insert (shipment4, address5) into ShipmentContainsDeliveryAddress

!insert (address4, geolocation4) into AddressContainsGeoLocation
!insert (address5, geolocation5) into AddressContainsGeoLocation

!insert (customer3, shipment4) into CustomerConsistsOfShipment
!insert (station2, shipment4) into StationShipment

!insert (station2, customer3) into StationContainsCustomer
!insert (station2, driver3) into StationContainsDriver
```
## Generation 2 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
222 Pine St, Gotham
```
```
111 Oak St, Metropolis
```

# Generation 3
```
!new Driver('driver4')
!driver4.id := 'D004'
!driver4.name := 'Olivia Brown'

!new Shipment('shipment5')
!shipment5.id := 'S005'
!shipment5.status := #NEW

!new Address('address6')
!address6.text := '555 Cedar St, Star City'

!new Address('address7')
!address7.text := '666 Birch St, Central City'

!new GeoLocation('geolocation6')
!geolocation6.latitude := 35.6895
!geolocation6.longitude := 139.6917

!new GeoLocation('geolocation7')
!geolocation7.latitude := 55.7558
!geolocation7.longitude := 37.6173

!new Customer('customer4')
!customer4.id := 'C004'
!customer4.name := 'Diana Prince'
!customer4.twitterUserName := '@dianaP'

!new Station('station3')

!insert (driver4, shipment5) into DriverShipment

!insert (shipment5, address6) into ShipmentContainsPickUpAddress
!insert (shipment5, address7) into ShipmentContainsDeliveryAddress

!insert (address6, geolocation6) into AddressContainsGeoLocation
!insert (address7, geolocation7) into AddressContainsGeoLocation

!insert (customer4, shipment5) into CustomerConsistsOfShipment
!insert (station3, shipment5) into StationShipment

!insert (station3, customer4) into StationContainsCustomer
!insert (station3, driver4) into StationContainsDriver
```
## Generation 3 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
666 Birch St, Central City
```
```
555 Cedar St, Star City
```

# Generation 4
```
!new Driver('driver5')
!driver5.id := 'D005'
!driver5.name := 'Logan Greene'

!new Shipment('shipment6')
!shipment6.id := 'S006'
!shipment6.status := #DELIVERED

!new Address('address8')
!address8.text := '777 Willow St, Coast City'

!new Address('address9')
!address9.text := '888 Poplar St, Blüdhaven'

!new GeoLocation('geolocation8')
!geolocation8.latitude := 30.2672
!geolocation8.longitude := -97.7431

!new GeoLocation('geolocation9')
!geolocation9.latitude := 41.8781
!geolocation9.longitude := -87.6298

!new Customer('customer5')
!customer5.id := 'C005'
!customer5.name := 'Clark Kent'
!customer5.twitterUserName := '@clarkK'

!new Station('station4')

!insert (driver5, shipment6) into DriverShipment

!insert (shipment6, address8) into ShipmentContainsPickUpAddress
!insert (shipment6, address9) into ShipmentContainsDeliveryAddress

!insert (address8, geolocation8) into AddressContainsGeoLocation
!insert (address9, geolocation9) into AddressContainsGeoLocation

!insert (customer5, shipment6) into CustomerConsistsOfShipment
!insert (station4, shipment6) into StationShipment

!insert (station4, customer5) into StationContainsCustomer
!insert (station4, driver5) into StationContainsDriver
```
## Generation 4 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 1 | 2 | 50.00% |
| Lat/Lon (out of valid addresses) | 0 | 1 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
888 Poplar St, Blüdhaven
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: 30.2672 Lon: -97.7431 for address: 777 Willow St, Coast City
```

# Generation 5
```
!new Driver('driver6')
!driver6.id := 'D006'
!driver6.name := 'Sophia Turner'

!new Shipment('shipment7')
!shipment7.id := 'S007'
!shipment7.status := #UNDERWAY

!new Address('address10')
!address10.text := '999 Cherry St, Keystone City'

!new Address('address11')
!address11.text := '1000 Bamboo St, Smallville'

!new GeoLocation('geolocation10')
!geolocation10.latitude := 52.5200
!geolocation10.longitude := 13.4050

!new GeoLocation('geolocation11')
!geolocation11.latitude := 39.9042
!geolocation11.longitude := 116.4074

!new Customer('customer6')
!customer6.id := 'C006'
!customer6.name := 'Peter Parker'
!customer6.twitterUserName := '@peterP'

!new Station('station5')

!insert (driver6, shipment7) into DriverShipment

!insert (shipment7, address10) into ShipmentContainsPickUpAddress
!insert (shipment7, address11) into ShipmentContainsDeliveryAddress

!insert (address10, geolocation10) into AddressContainsGeoLocation
!insert (address11, geolocation11) into AddressContainsGeoLocation

!insert (customer6, shipment7) into CustomerConsistsOfShipment
!insert (station5, shipment7) into StationShipment

!insert (station5, customer6) into StationContainsCustomer
!insert (station5, driver6) into StationContainsDriver
```
## Generation 5 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
999 Cherry St, Keystone City
```
```
1000 Bamboo St, Smallville
```

# Generation 6
```
!new Driver('driver7')
!driver7.id := 'D007'
!driver7.name := 'Ethan Hunt'

!new Shipment('shipment8')
!shipment8.id := 'S008'
!shipment8.status := #NEW

!new Address('address12')
!address12.text := '1111 Maple Lane, Gotham City'

!new Address('address13')
!address13.text := '2222 Elm Place, Metropolis'

!new GeoLocation('geolocation12')
!geolocation12.latitude := 25.7617
!geolocation12.longitude := -80.1918

!new GeoLocation('geolocation13')
!geolocation13.latitude := 28.5383
!geolocation13.longitude := -81.3792

!new Customer('customer7')
!customer7.id := 'C007'
!customer7.name := 'Tony Stark'
!customer7.twitterUserName := '@tonyS'

!new Station('station6')

!insert (driver7, shipment8) into DriverShipment

!insert (shipment8, address12) into ShipmentContainsPickUpAddress
!insert (shipment8, address13) into ShipmentContainsDeliveryAddress

!insert (address12, geolocation12) into AddressContainsGeoLocation
!insert (address13, geolocation13) into AddressContainsGeoLocation

!insert (customer7, shipment8) into CustomerConsistsOfShipment
!insert (station6, shipment8) into StationShipment

!insert (station6, customer7) into StationContainsCustomer
!insert (station6, driver7) into StationContainsDriver
```
## Generation 6 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
1111 Maple Lane, Gotham City
```
```
2222 Elm Place, Metropolis
```

# Generation 7
```
!new Driver('driver8')
!driver8.id := 'D008'
!driver8.name := 'Natalie Williams'

!new Shipment('shipment9')
!shipment9.id := 'S009'
!shipment9.status := #ASSIGNED

!new Address('address14')
!address14.text := '3333 Summer St, Starling City'

!new Address('address15')
!address15.text := '4444 Winter Rd, Central City'

!new GeoLocation('geolocation14')
!geolocation14.latitude := 40.7306
!geolocation14.longitude := -73.9352

!new GeoLocation('geolocation15')
!geolocation15.latitude := 34.0522
!geolocation15.longitude := -118.2437

!new Customer('customer8')
!customer8.id := 'C008'
!customer8.name := 'Bruce Banner'
!customer8.twitterUserName := '@bruceB'

!new Station('station7')

!insert (driver8, shipment9) into DriverShipment

!insert (shipment9, address14) into ShipmentContainsPickUpAddress
!insert (shipment9, address15) into ShipmentContainsDeliveryAddress

!insert (address14, geolocation14) into AddressContainsGeoLocation
!insert (address15, geolocation15) into AddressContainsGeoLocation

!insert (customer8, shipment9) into CustomerConsistsOfShipment
!insert (station7, shipment9) into StationShipment

!insert (station7, customer8) into StationContainsCustomer
!insert (station7, driver8) into StationContainsDriver
```
## Generation 7 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
3333 Summer St, Starling City
```
```
4444 Winter Rd, Central City
```

# Generation 8
```
!new Driver('driver9')
!driver9.id := 'D009'
!driver9.name := 'Michelle Carter'

!new Shipment('shipment10')
!shipment10.id := 'S010'
!shipment10.status := #UNDERWAY

!new Address('address16')
!address16.text := '5555 Willow Ave, National City'

!new Address('address17')
!address17.text := '6666 Pine Blvd, Coast City'

!new GeoLocation('geolocation16')
!geolocation16.latitude := 33.7488
!geolocation16.longitude := -84.3880

!new GeoLocation('geolocation17')
!geolocation17.latitude := 29.7604
!geolocation17.longitude := -95.3698

!new Customer('customer9')
!customer9.id := 'C009'
!customer9.name := 'Natasha Romanoff'
!customer9.twitterUserName := '@natashaR'

!new Station('station8')

!insert (driver9, shipment10) into DriverShipment

!insert (shipment10, address16) into ShipmentContainsPickUpAddress
!insert (shipment10, address17) into ShipmentContainsDeliveryAddress

!insert (address16, geolocation16) into AddressContainsGeoLocation
!insert (address17, geolocation17) into AddressContainsGeoLocation

!insert (customer9, shipment10) into CustomerConsistsOfShipment
!insert (station8, shipment10) into StationShipment

!insert (station8, customer9) into StationContainsCustomer
!insert (station8, driver9) into StationContainsDriver
```
## Generation 8 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
5555 Willow Ave, National City
```
```
6666 Pine Blvd, Coast City
```

# Generation 9
```
!new Driver('driver10')
!driver10.id := 'D010'
!driver10.name := 'Oliver Queen'

!new Shipment('shipment11')
!shipment11.id := 'S011'
!shipment11.status := #DELIVERED

!new Address('address18')
!address18.text := '7777 Oak Dr, Atlantis'

!new Address('address19')
!address19.text := '8888 Birch St, Wakanda'

!new GeoLocation('geolocation18')
!geolocation18.latitude := 60.1699
!geolocation18.longitude := 24.9384

!new GeoLocation('geolocation19')
!geolocation19.latitude := 35.6895
!geolocation19.longitude := 139.6917

!new Customer('customer10')
!customer10.id := 'C010'
!customer10.name := 'Diana Prince'
!customer10.twitterUserName := '@wonderWoman'

!new Station('station9')

!insert (driver10, shipment11) into DriverShipment

!insert (shipment11, address18) into ShipmentContainsPickUpAddress
!insert (shipment11, address19) into ShipmentContainsDeliveryAddress

!insert (address18, geolocation18) into AddressContainsGeoLocation
!insert (address19, geolocation19) into AddressContainsGeoLocation

!insert (customer10, shipment11) into CustomerConsistsOfShipment
!insert (station9, shipment11) into StationShipment

!insert (station9, customer10) into StationContainsCustomer
!insert (station9, driver10) into StationContainsDriver
```
## Generation 9 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
7777 Oak Dr, Atlantis
```
```
8888 Birch St, Wakanda
```

# Generation 10
```
!new Driver('driver11')
!driver11.id := 'D011'
!driver11.name := 'Jack Reacher'

!new Shipment('shipment12')
!shipment12.id := 'S012'
!shipment12.status := #DELIVERED

!new Address('address20')
!address20.text := '1010 Cypress St, Elms Town'

!new Address('address21')
!address21.text := '2020 Maple Rd, Timber City'

!new GeoLocation('geolocation20')
!geolocation20.latitude := 23.6345
!geolocation20.longitude := -102.5528

!new GeoLocation('geolocation21')
!geolocation21.latitude := 19.4326
!geolocation21.longitude := -99.1332

!new Customer('customer11')
!customer11.id := 'C011'
!customer11.name := 'Steve Rogers'
!customer11.twitterUserName := '@captainAmerica'

!new Station('station10')

!insert (driver11, shipment12) into DriverShipment

!insert (shipment12, address20) into ShipmentContainsPickUpAddress
!insert (shipment12, address21) into ShipmentContainsDeliveryAddress

!insert (address20, geolocation20) into AddressContainsGeoLocation
!insert (address21, geolocation21) into AddressContainsGeoLocation

!insert (customer11, shipment12) into CustomerConsistsOfShipment
!insert (station10, shipment12) into StationShipment

!insert (station10, customer11) into StationContainsCustomer
!insert (station10, driver11) into StationContainsDriver
```
## Generation 10 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
1010 Cypress St, Elms Town
```
```
2020 Maple Rd, Timber City
```

# Generation 11
```
!new Driver('driver12')
!driver12.id := 'D012'
!driver12.name := 'John Doe'

!new Shipment('shipment13')
!shipment13.id := 'S013'
!shipment13.status := #NEW

!new Address('address22')
!address22.text := '3030 Cedar St, Hill Valley'

!new Address('address23')
!address23.text := '4040 Aspen Ave, Twin Peaks'

!new GeoLocation('geolocation22')
!geolocation22.latitude := 51.1657
!geolocation22.longitude := 10.4515

!new GeoLocation('geolocation23')
!geolocation23.latitude := 31.2304
!geolocation23.longitude := 121.4737

!new Customer('customer12')
!customer12.id := 'C012'
!customer12.name := 'Clark Kent'
!customer12.twitterUserName := '@superman'

!new Station('station11')

!insert (driver12, shipment13) into DriverShipment

!insert (shipment13, address22) into ShipmentContainsPickUpAddress
!insert (shipment13, address23) into ShipmentContainsDeliveryAddress

!insert (address22, geolocation22) into AddressContainsGeoLocation
!insert (address23, geolocation23) into AddressContainsGeoLocation

!insert (customer12, shipment13) into CustomerConsistsOfShipment
!insert (station11, shipment13) into StationShipment

!insert (station11, customer12) into StationContainsCustomer
!insert (station11, driver12) into StationContainsDriver
```
## Generation 11 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
3030 Cedar St, Hill Valley
```
```
4040 Aspen Ave, Twin Peaks
```

# Generation 12
```
!new Driver('driver13')
!driver13.id := 'D013'
!driver13.name := 'Lara Croft'

!new Shipment('shipment14')
!shipment14.id := 'S014'
!shipment14.status := #ASSIGNED

!new Address('address24')
!address24.text := '5050 Chestnut Rd, Emerald City'

!new Address('address25')
!address25.text := '6060 Pine Lane, Neverland'

!new GeoLocation('geolocation24')
!geolocation24.latitude := 55.7558
!geolocation24.longitude := 37.6173

!new GeoLocation('geolocation25')
!geolocation25.latitude := -33.8688
!geolocation25.longitude := 151.2093

!new Customer('customer13')
!customer13.id := 'C013'
!customer13.name := 'Peter Parker'
!customer13.twitterUserName := '@spidey'

!new Station('station12')

!insert (driver13, shipment14) into DriverShipment

!insert (shipment14, address24) into ShipmentContainsPickUpAddress
!insert (shipment14, address25) into ShipmentContainsDeliveryAddress

!insert (address24, geolocation24) into AddressContainsGeoLocation
!insert (address25, geolocation25) into AddressContainsGeoLocation

!insert (customer13, shipment14) into CustomerConsistsOfShipment
!insert (station12, shipment14) into StationShipment

!insert (station12, customer13) into StationContainsCustomer
!insert (station12, driver13) into StationContainsDriver
```
## Generation 12 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
5050 Chestnut Rd, Emerald City
```
```
6060 Pine Lane, Neverland
```

# Generation 13
```
!new Driver('driver14')
!driver14.id := 'D014'
!driver14.name := 'James Bond'

!new Shipment('shipment15')
!shipment15.id := 'S015'
!shipment15.status := #UNDERWAY

!new Address('address26')
!address26.text := '7070 Birch St, Gotham Valley'

!new Address('address27')
!address27.text := '8080 Elm Blvd, Metropolis Heights'

!new GeoLocation('geolocation26')
!geolocation26.latitude := 41.9028
!geolocation26.longitude := 12.4964

!new GeoLocation('geolocation27')
!geolocation27.latitude := 35.6895
!geolocation27.longitude := 139.6917

!new Customer('customer14')
!customer14.id := 'C014'
!customer14.name := 'Bruce Wayne'
!customer14.twitterUserName := '@darkKnight'

!new Station('station13')

!insert (driver14, shipment15) into DriverShipment

!insert (shipment15, address26) into ShipmentContainsPickUpAddress
!insert (shipment15, address27) into ShipmentContainsDeliveryAddress

!insert (address26, geolocation26) into AddressContainsGeoLocation
!insert (address27, geolocation27) into AddressContainsGeoLocation

!insert (customer14, shipment15) into CustomerConsistsOfShipment
!insert (station13, shipment15) into StationShipment

!insert (station13, customer14) into StationContainsCustomer
!insert (station13, driver14) into StationContainsDriver
```
## Generation 13 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
7070 Birch St, Gotham Valley
```
```
8080 Elm Blvd, Metropolis Heights
```

# Generation 14
```
!new Driver('driver15')
!driver15.id := 'D015'
!driver15.name := 'Jessica Jones'

!new Shipment('shipment16')
!shipment16.id := 'S016'
!shipment16.status := #NEW

!new Address('address28')
!address28.text := '9090 Maple St, Riverdale'

!new Address('address29')
!address29.text := '1010 Oak Ct, Springfield'

!new GeoLocation('geolocation28')
!geolocation28.latitude := 48.8566
!geolocation28.longitude := 2.3522

!new GeoLocation('geolocation29')
!geolocation29.latitude := 34.0522
!geolocation29.longitude := -118.2437

!new Customer('customer15')
!customer15.id := 'C015'
!customer15.name := 'Tony Stark'
!customer15.twitterUserName := '@ironMan'

!new Station('station14')

!insert (driver15, shipment16) into DriverShipment

!insert (shipment16, address28) into ShipmentContainsPickUpAddress
!insert (shipment16, address29) into ShipmentContainsDeliveryAddress

!insert (address28, geolocation28) into AddressContainsGeoLocation
!insert (address29, geolocation29) into AddressContainsGeoLocation

!insert (customer15, shipment16) into CustomerConsistsOfShipment
!insert (station14, shipment16) into StationShipment

!insert (station14, customer15) into StationContainsCustomer
!insert (station14, driver15) into StationContainsDriver
```
## Generation 14 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
9090 Maple St, Riverdale
```
```
1010 Oak Ct, Springfield
```

# Generation 15
```
!new Driver('driver16')
!driver16.id := 'D016'
!driver16.name := 'Sarah Connor'

!new Shipment('shipment17')
!shipment17.id := 'S017'
!shipment17.status := #ASSIGNED

!new Address('address30')
!address30.text := '2020 Cedar Way, Sky City'

!new Address('address31')
!address31.text := '3030 Pine Hill, Forest Town'

!new GeoLocation('geolocation30')
!geolocation30.latitude := 51.5074
!geolocation30.longitude := -0.1278

!new GeoLocation('geolocation31')
!geolocation31.latitude := 37.7749
!geolocation31.longitude := -122.4194

!new Customer('customer16')
!customer16.id := 'C016'
!customer16.name := 'Peter Quill'
!customer16.twitterUserName := '@starlord'

!new Station('station15')

!insert (driver16, shipment17) into DriverShipment

!insert (shipment17, address30) into ShipmentContainsPickUpAddress
!insert (shipment17, address31) into ShipmentContainsDeliveryAddress

!insert (address30, geolocation30) into AddressContainsGeoLocation
!insert (address31, geolocation31) into AddressContainsGeoLocation

!insert (customer16, shipment17) into CustomerConsistsOfShipment
!insert (station15, shipment17) into StationShipment

!insert (station15, customer16) into StationContainsCustomer
!insert (station15, driver16) into StationContainsDriver
```
## Generation 15 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
2020 Cedar Way, Sky City
```
```
3030 Pine Hill, Forest Town
```

# Generation 16
```
!new Driver('driver17')
!driver17.id := 'D017'
!driver17.name := 'Rick Deckard'

!new Shipment('shipment18')
!shipment18.id := 'S018'
!shipment18.status := #DELIVERED

!new Address('address32')
!address32.text := '4040 Oak Road, Deckard City'

!new Address('address33')
!address33.text := '5050 Spruce Street, Replicant Town'

!new GeoLocation('geolocation32')
!geolocation32.latitude := 40.4168
!geolocation32.longitude := -3.7038

!new GeoLocation('geolocation33')
!geolocation33.latitude := -23.5505
!geolocation33.longitude := -46.6333

!new Customer('customer17')
!customer17.id := 'C017'
!customer17.name := 'Ellen Ripley'
!customer17.twitterUserName := '@alienHunter'

!new Station('station16')

!insert (driver17, shipment18) into DriverShipment

!insert (shipment18, address32) into ShipmentContainsPickUpAddress
!insert (shipment18, address33) into ShipmentContainsDeliveryAddress

!insert (address32, geolocation32) into AddressContainsGeoLocation
!insert (address33, geolocation33) into AddressContainsGeoLocation

!insert (customer17, shipment18) into CustomerConsistsOfShipment
!insert (station16, shipment18) into StationShipment

!insert (station16, customer17) into StationContainsCustomer
!insert (station16, driver17) into StationContainsDriver
```
## Generation 16 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 1 | 2 | 50.00% |
| Lat/Lon (out of valid addresses) | 0 | 1 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
4040 Oak Road, Deckard City
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: -23.5505 Lon: -46.6333 for address: 5050 Spruce Street, Replicant Town
```

# Generation 17
```
!new Driver('driver18')
!driver18.id := 'D018'
!driver18.name := 'Ethan Edwards'

!new Shipment('shipment19')
!shipment19.id := 'S019'
!shipment19.status := #NEW

!new Address('address34')
!address34.text := '6060 Redwood Lane, Frontier City'

!new Address('address35')
!address35.text := '7070 Aspen Trail, Prairie Town'

!new GeoLocation('geolocation34')
!geolocation34.latitude := 59.3293
!geolocation34.longitude := 18.0686

!new GeoLocation('geolocation35')
!geolocation35.latitude := 35.6895
!geolocation35.longitude := 139.6917

!new Customer('customer18')
!customer18.id := 'C018'
!customer18.name := 'Marty McFly'
!customer18.twitterUserName := '@back2future'

!new Station('station17')

!insert (driver18, shipment19) into DriverShipment

!insert (shipment19, address34) into ShipmentContainsPickUpAddress
!insert (shipment19, address35) into ShipmentContainsDeliveryAddress

!insert (address34, geolocation34) into AddressContainsGeoLocation
!insert (address35, geolocation35) into AddressContainsGeoLocation

!insert (customer18, shipment19) into CustomerConsistsOfShipment
!insert (station17, shipment19) into StationShipment

!insert (station17, customer18) into StationContainsCustomer
!insert (station17, driver18) into StationContainsDriver
```
## Generation 17 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
6060 Redwood Lane, Frontier City
```
```
7070 Aspen Trail, Prairie Town
```

# Generation 18
```
!new Driver('driver19')
!driver19.id := 'D019'
!driver19.name := 'Frodo Baggins'

!new Shipment('shipment20')
!shipment20.id := 'S020'
!shipment20.status := #ASSIGNED

!new Address('address36')
!address36.text := '8080 Hobbiton Rd, Shire Town'

!new Address('address37')
!address37.text := '9090 Mordor Ave, Shadow City'

!new GeoLocation('geolocation36')
!geolocation36.latitude := 41.9029
!geolocation36.longitude := 12.4534

!new GeoLocation('geolocation37')
!geolocation37.latitude := 52.3676
!geolocation37.longitude := 4.9041

!new Customer('customer19')
!customer19.id := 'C019'
!customer19.name := 'Gandalf the Grey'
!customer19.twitterUserName := '@wizardGandalf'

!new Station('station18')

!insert (driver19, shipment20) into DriverShipment

!insert (shipment20, address36) into ShipmentContainsPickUpAddress
!insert (shipment20, address37) into ShipmentContainsDeliveryAddress

!insert (address36, geolocation36) into AddressContainsGeoLocation
!insert (address37, geolocation37) into AddressContainsGeoLocation

!insert (customer19, shipment20) into CustomerConsistsOfShipment
!insert (station18, shipment20) into StationShipment

!insert (station18, customer19) into StationContainsCustomer
!insert (station18, driver19) into StationContainsDriver
```
## Generation 18 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
8080 Hobbiton Rd, Shire Town
```
```
9090 Mordor Ave, Shadow City
```

# Generation 19
```
!new Driver('driver20')
!driver20.id := 'D020'
!driver20.name := 'Katniss Everdeen'

!new Shipment('shipment21')
!shipment21.id := 'S021'
!shipment21.status := #UNDERWAY

!new Address('address38')
!address38.text := '1111 Capitol Rd, Panem City'

!new Address('address39')
!address39.text := '2222 District Ave, Seam Village'

!new GeoLocation('geolocation38')
!geolocation38.latitude := 40.7128
!geolocation38.longitude := -74.0060

!new GeoLocation('geolocation39')
!geolocation39.latitude := 37.7749
!geolocation39.longitude := -122.4194

!new Customer('customer20')
!customer20.id := 'C020'
!customer20.name := 'Peeta Mellark'
!customer20.twitterUserName := '@peetaM'

!new Station('station19')

!insert (driver20, shipment21) into DriverShipment

!insert (shipment21, address38) into ShipmentContainsPickUpAddress
!insert (shipment21, address39) into ShipmentContainsDeliveryAddress

!insert (address38, geolocation38) into AddressContainsGeoLocation
!insert (address39, geolocation39) into AddressContainsGeoLocation

!insert (customer20, shipment21) into CustomerConsistsOfShipment
!insert (station19, shipment21) into StationShipment

!insert (station19, customer20) into StationContainsCustomer
!insert (station19, driver20) into StationContainsDriver
```
## Generation 19 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
1111 Capitol Rd, Panem City
```
```
2222 District Ave, Seam Village
```

# Generation 20
```
!new Driver('driver21')
!driver21.id := 'D021'
!driver21.name := 'Arya Stark'

!new Shipment('shipment22')
!shipment22.id := 'S022'
!shipment22.status := #DELIVERED

!new Address('address40')
!address40.text := '3333 Kings Landing Rd, Westeros'

!new Address('address41')
!address41.text := '4444 Winterfell Way, North Kingdom'

!new GeoLocation('geolocation40')
!geolocation40.latitude := 51.1657
!geolocation40.longitude := 10.4515

!new GeoLocation('geolocation41')
!geolocation41.latitude := 55.7558
!geolocation41.longitude := 37.6173

!new Customer('customer21')
!customer21.id := 'C021'
!customer21.name := 'Jon Snow'
!customer21.twitterUserName := '@kingInTheNorth'

!new Station('station20')

!insert (driver21, shipment22) into DriverShipment

!insert (shipment22, address40) into ShipmentContainsPickUpAddress
!insert (shipment22, address41) into ShipmentContainsDeliveryAddress

!insert (address40, geolocation40) into AddressContainsGeoLocation
!insert (address41, geolocation41) into AddressContainsGeoLocation

!insert (customer21, shipment22) into CustomerConsistsOfShipment
!insert (station20, shipment22) into StationShipment

!insert (station20, customer21) into StationContainsCustomer
!insert (station20, driver21) into StationContainsDriver
```
## Generation 20 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 1 | 2 | 50.00% |
| Lat/Lon (out of valid addresses) | 0 | 1 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
4444 Winterfell Way, North Kingdom
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: 51.1657 Lon: 10.4515 for address: 3333 Kings Landing Rd, Westeros
```

# Generation 21
```
!new Driver('driver22')
!driver22.id := 'D022'
!driver22.name := 'Bilbo Baggins'

!new Shipment('shipment23')
!shipment23.id := 'S023'
!shipment23.status := #UNDERWAY

!new Address('address42')
!address42.text := '5555 Hobbiton Path, Shire District'

!new Address('address43')
!address43.text := '6666 Rivendell Ct, Elven Realm'

!new GeoLocation('geolocation42')
!geolocation42.latitude := 48.8566
!geolocation42.longitude := 2.3522

!new GeoLocation('geolocation43')
!geolocation43.latitude := 41.8902
!geolocation43.longitude := 12.4922

!new Customer('customer22')
!customer22.id := 'C022'
!customer22.name := 'Samwise Gamgee'
!customer22.twitterUserName := '@faithfulSam'

!new Station('station21')

!insert (driver22, shipment23) into DriverShipment

!insert (shipment23, address42) into ShipmentContainsPickUpAddress
!insert (shipment23, address43) into ShipmentContainsDeliveryAddress

!insert (address42, geolocation42) into AddressContainsGeoLocation
!insert (address43, geolocation43) into AddressContainsGeoLocation

!insert (customer22, shipment23) into CustomerConsistsOfShipment
!insert (station21, shipment23) into StationShipment

!insert (station21, customer22) into StationContainsCustomer
!insert (station21, driver22) into StationContainsDriver
```
## Generation 21 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
5555 Hobbiton Path, Shire District
```
```
6666 Rivendell Ct, Elven Realm
```

# Generation 22
```
!new Driver('driver23')
!driver23.id := 'D023'
!driver23.name := 'Neo Anderson'

!new Shipment('shipment24')
!shipment24.id := 'S024'
!shipment24.status := #ASSIGNED

!new Address('address44')
!address44.text := '7777 Zion Blvd, Matrix City'

!new Address('address45')
!address45.text := '8888 Network Ln, Code Valley'

!new GeoLocation('geolocation44')
!geolocation44.latitude := 34.0522
!geolocation44.longitude := -118.2437

!new GeoLocation('geolocation45')
!geolocation45.latitude := 51.5074
!geolocation45.longitude := -0.1278

!new Customer('customer23')
!customer23.id := 'C023'
!customer23.name := 'Trinity'
!customer23.twitterUserName := '@matrixFight'

!new Station('station22')

!insert (driver23, shipment24) into DriverShipment

!insert (shipment24, address44) into ShipmentContainsPickUpAddress
!insert (shipment24, address45) into ShipmentContainsDeliveryAddress

!insert (address44, geolocation44) into AddressContainsGeoLocation
!insert (address45, geolocation45) into AddressContainsGeoLocation

!insert (customer23, shipment24) into CustomerConsistsOfShipment
!insert (station22, shipment24) into StationShipment

!insert (station22, customer23) into StationContainsCustomer
!insert (station22, driver23) into StationContainsDriver
```
## Generation 22 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
7777 Zion Blvd, Matrix City
```
```
8888 Network Ln, Code Valley
```

# Generation 23
```
!new Driver('driver24')
!driver24.id := 'D024'
!driver24.name := 'Ellen Ripley'

!new Shipment('shipment25')
!shipment25.id := 'S025'
!shipment25.status := #NEW

!new Address('address46')
!address46.text := '9999 Nostromo St, LV-426 Colony'

!new Address('address47')
!address47.text := '1010 Sulaco Ave, Gateway Station'

!new GeoLocation('geolocation46')
!geolocation46.latitude := 48.2082
!geolocation46.longitude := 16.3738

!new GeoLocation('geolocation47')
!geolocation47.latitude := 35.6895
!geolocation47.longitude := 139.6917

!new Customer('customer24')
!customer24.id := 'C024'
!customer24.name := 'Amanda Ripley'
!customer24.twitterUserName := '@survivorAmanda'

!new Station('station23')

!insert (driver24, shipment25) into DriverShipment

!insert (shipment25, address46) into ShipmentContainsPickUpAddress
!insert (shipment25, address47) into ShipmentContainsDeliveryAddress

!insert (address46, geolocation46) into AddressContainsGeoLocation
!insert (address47, geolocation47) into AddressContainsGeoLocation

!insert (customer24, shipment25) into CustomerConsistsOfShipment
!insert (station23, shipment25) into StationShipment

!insert (station23, customer24) into StationContainsCustomer
!insert (station23, driver24) into StationContainsDriver
```
## Generation 23 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
9999 Nostromo St, LV-426 Colony
```
```
1010 Sulaco Ave, Gateway Station
```

# Generation 24
```
!new Driver('driver25')
!driver25.id := 'D025'
!driver25.name := 'Captain Kirk'

!new Shipment('shipment26')
!shipment26.id := 'S026'
!shipment26.status := #DELIVERED

!new Address('address48')
!address48.text := '1212 Enterprise Blvd, Starfleet HQ'

!new Address('address49')
!address49.text := '2323 Vulcan St, Spock City'

!new GeoLocation('geolocation48')
!geolocation48.latitude := 45.4642
!geolocation48.longitude := 9.1900

!new GeoLocation('geolocation49')
!geolocation49.latitude := 35.6762
!geolocation49.longitude := 139.6503

!new Customer('customer25')
!customer25.id := 'C025'
!customer25.name := 'Mr. Spock'
!customer25.twitterUserName := '@logicalSpock'

!new Station('station24')

!insert (driver25, shipment26) into DriverShipment

!insert (shipment26, address48) into ShipmentContainsPickUpAddress
!insert (shipment26, address49) into ShipmentContainsDeliveryAddress

!insert (address48, geolocation48) into AddressContainsGeoLocation
!insert (address49, geolocation49) into AddressContainsGeoLocation

!insert (customer25, shipment26) into CustomerConsistsOfShipment
!insert (station24, shipment26) into StationShipment

!insert (station24, customer25) into StationContainsCustomer
!insert (station24, driver25) into StationContainsDriver
```
## Generation 24 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 1 | 2 | 50.00% |
| Lat/Lon (out of valid addresses) | 0 | 1 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
2323 Vulcan St, Spock City
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: 45.4642 Lon: 9.19 for address: 1212 Enterprise Blvd, Starfleet HQ
```

# Generation 25
```
!new Driver('driver26')
!driver26.id := 'D026'
!driver26.name := 'Tyrion Lannister'

!new Shipment('shipment27')
!shipment27.id := 'S027'
!shipment27.status := #ASSIGNED

!new Address('address50')
!address50.text := '3030 Dragonstone St, Westeros Isle'

!new Address('address51')
!address51.text := '4040 Casterly Rock Dr, Lannister City'

!new GeoLocation('geolocation50')
!geolocation50.latitude := 33.7490
!geolocation50.longitude := -84.3880

!new GeoLocation('geolocation51')
!geolocation51.latitude := 41.3851
!geolocation51.longitude := 2.1734

!new Customer('customer26')
!customer26.id := 'C026'
!customer26.name := 'Daenerys Targaryen'
!customer26.twitterUserName := '@dragonQueen'

!new Station('station25')

!insert (driver26, shipment27) into DriverShipment

!insert (shipment27, address50) into ShipmentContainsPickUpAddress
!insert (shipment27, address51) into ShipmentContainsDeliveryAddress

!insert (address50, geolocation50) into AddressContainsGeoLocation
!insert (address51, geolocation51) into AddressContainsGeoLocation

!insert (customer26, shipment27) into CustomerConsistsOfShipment
!insert (station25, shipment27) into StationShipment

!insert (station25, customer26) into StationContainsCustomer
!insert (station25, driver26) into StationContainsDriver
```
## Generation 25 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
4040 Casterly Rock Dr, Lannister City
```
```
3030 Dragonstone St, Westeros Isle
```

# Generation 26
```
!new Driver('driver27')
!driver27.id := 'D027'
!driver27.name := 'Han Solo'

!new Shipment('shipment28')
!shipment28.id := 'S028'
!shipment28.status := #NEW

!new Address('address52')
!address52.text := '5050 Millennium Falcon Path, Corellia System'

!new Address('address53')
!address53.text := '6060 Tatooine Circle, Outer Rim Territories'

!new GeoLocation('geolocation52')
!geolocation52.latitude := 29.9792
!geolocation52.longitude := 31.1342

!new GeoLocation('geolocation53')
!geolocation53.latitude := 21.3069
!geolocation53.longitude := -157.8583

!new Customer('customer27')
!customer27.id := 'C027'
!customer27.name := 'Leia Organa'
!customer27.twitterUserName := '@princessLeia'

!new Station('station26')

!insert (driver27, shipment28) into DriverShipment

!insert (shipment28, address52) into ShipmentContainsPickUpAddress
!insert (shipment28, address53) into ShipmentContainsDeliveryAddress

!insert (address52, geolocation52) into AddressContainsGeoLocation
!insert (address53, geolocation53) into AddressContainsGeoLocation

!insert (customer27, shipment28) into CustomerConsistsOfShipment
!insert (station26, shipment28) into StationShipment

!insert (station26, customer27) into StationContainsCustomer
!insert (station26, driver27) into StationContainsDriver
```
## Generation 26 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
5050 Millennium Falcon Path, Corellia System
```
```
6060 Tatooine Circle, Outer Rim Territories
```

# Generation 27
```
!new Driver('driver28')
!driver28.id := 'D028'
!driver28.name := 'Hermione Granger'

!new Shipment('shipment29')
!shipment29.id := 'S029'
!shipment29.status := #UNDERWAY

!new Address('address54')
!address54.text := '7070 Diagon Alley, Wizard Town'

!new Address('address55')
!address55.text := '8080 Hogwarts St, Magic City'

!new GeoLocation('geolocation54')
!geolocation54.latitude := 51.5074
!geolocation54.longitude := -0.1278

!new GeoLocation('geolocation55')
!geolocation55.latitude := 55.3781
!geolocation55.longitude := -3.4360

!new Customer('customer28')
!customer28.id := 'C028'
!customer28.name := 'Harry Potter'
!customer28.twitterUserName := '@chosenOne'

!new Station('station27')

!insert (driver28, shipment29) into DriverShipment

!insert (shipment29, address54) into ShipmentContainsPickUpAddress
!insert (shipment29, address55) into ShipmentContainsDeliveryAddress

!insert (address54, geolocation54) into AddressContainsGeoLocation
!insert (address55, geolocation55) into AddressContainsGeoLocation

!insert (customer28, shipment29) into CustomerConsistsOfShipment
!insert (station27, shipment29) into StationShipment

!insert (station27, customer28) into StationContainsCustomer
!insert (station27, driver28) into StationContainsDriver
```
## Generation 27 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
7070 Diagon Alley, Wizard Town
```
```
8080 Hogwarts St, Magic City
```

# Generation 28
```
!new Driver('driver29')
!driver29.id := 'D029'
!driver29.name := 'Indiana Jones'

!new Shipment('shipment30')
!shipment30.id := 'S030'
!shipment30.status := #ASSIGNED

!new Address('address56')
!address56.text := '9090 Adventure Ave, Archaeologist City'

!new Address('address57')
!address57.text := '1011 Temple St, Lost Kingdom'

!new GeoLocation('geolocation56')
!geolocation56.latitude := 30.0444
!geolocation56.longitude := 31.2357

!new GeoLocation('geolocation57')
!geolocation57.latitude := 27.1751
!geolocation57.longitude := 78.0421

!new Customer('customer29')
!customer29.id := 'C029'
!customer29.name := 'Marion Ravenwood'
!customer29.twitterUserName := '@marionR'

!new Station('station28')

!insert (driver29, shipment30) into DriverShipment

!insert (shipment30, address56) into ShipmentContainsPickUpAddress
!insert (shipment30, address57) into ShipmentContainsDeliveryAddress

!insert (address56, geolocation56) into AddressContainsGeoLocation
!insert (address57, geolocation57) into AddressContainsGeoLocation

!insert (customer29, shipment30) into CustomerConsistsOfShipment
!insert (station28, shipment30) into StationShipment

!insert (station28, customer29) into StationContainsCustomer
!insert (station28, driver29) into StationContainsDriver
```
## Generation 28 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
9090 Adventure Ave, Archaeologist City
```
```
1011 Temple St, Lost Kingdom
```

# Generation 29
```
!new Driver('driver30')
!driver30.id := 'D030'
!driver30.name := 'James T. Kirk'

!new Shipment('shipment31')
!shipment31.id := 'S031'
!shipment31.status := #NEW

!new Address('address58')
!address58.text := '1112 Starfleet Headquarters, San Francisco'

!new Address('address59')
!address59.text := '1213 Vulcan Academy, ShiKahr'

!new GeoLocation('geolocation58')
!geolocation58.latitude := 37.7749
!geolocation58.longitude := -122.4194

!new GeoLocation('geolocation59')
!geolocation59.latitude := -33.8688
!geolocation59.longitude := 151.2093

!new Customer('customer30')
!customer30.id := 'C030'
!customer30.name := 'Leonard McCoy'
!customer30.twitterUserName := '@bonesMcCoy'

!new Station('station29')

!insert (driver30, shipment31) into DriverShipment

!insert (shipment31, address58) into ShipmentContainsPickUpAddress
!insert (shipment31, address59) into ShipmentContainsDeliveryAddress

!insert (address58, geolocation58) into AddressContainsGeoLocation
!insert (address59, geolocation59) into AddressContainsGeoLocation

!insert (customer30, shipment31) into CustomerConsistsOfShipment
!insert (station29, shipment31) into StationShipment

!insert (station29, customer30) into StationContainsCustomer
!insert (station29, driver30) into StationContainsDriver
```
## Generation 29 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
1112 Starfleet Headquarters, San Francisco
```
```
1213 Vulcan Academy, ShiKahr
```

# Generation 30
```
!new Driver('driver31')
!driver31.id := 'D031'
!driver31.name := 'Yoda'

!new Shipment('shipment32')
!shipment32.id := 'S032'
!shipment32.status := #DELIVERED

!new Address('address60')
!address60.text := '1414 Jedi Temple, Coruscant'

!new Address('address61')
!address61.text := '1515 Dagobah System, Outer Rim'

!new GeoLocation('geolocation60')
!geolocation60.latitude := 36.2048
!geolocation60.longitude := 138.2529

!new GeoLocation('geolocation61')
!geolocation61.latitude := 19.8968
!geolocation61.longitude := -155.5828

!new Customer('customer31')
!customer31.id := 'C031'
!customer31.name := 'Obi-Wan Kenobi'
!customer31.twitterUserName := '@generalKenobi'

!new Station('station30')

!insert (driver31, shipment32) into DriverShipment

!insert (shipment32, address60) into ShipmentContainsPickUpAddress
!insert (shipment32, address61) into ShipmentContainsDeliveryAddress

!insert (address60, geolocation60) into AddressContainsGeoLocation
!insert (address61, geolocation61) into AddressContainsGeoLocation

!insert (customer31, shipment32) into CustomerConsistsOfShipment
!insert (station30, shipment32) into StationShipment

!insert (station30, customer31) into StationContainsCustomer
!insert (station30, driver31) into StationContainsDriver
```
## Generation 30 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 0 | 2 | 0.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
1414 Jedi Temple, Coruscant
```
```
1515 Dagobah System, Outer Rim
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | GPT_4O | 
| Type | Simple | 
| System | pickupnet | 
| Number of generations | 30 | 

| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 4 | 
| Invariants Errors | 1 | 

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment2' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```

| Invariants Errors | 
|---| 
```
checking invariant (3) `Shipment::differentPickupAndDeliveryAddress': FAILED.
```

| PickupNet | Valid | Total | Success (%) | 
|---|---|---|---| 
| Address | 6 | 61 | 9.84% |
| Lat/Lon (out of valid addresses) | 0 | 6 | 0.00% |
| Twitter | 31 | 31 | 100.00% |

| Invalid Addresses | 
|---| 
```
789 Maple St, Shelbyville
```
```
222 Pine St, Gotham
```
```
111 Oak St, Metropolis
```
```
666 Birch St, Central City
```
```
555 Cedar St, Star City
```
```
888 Poplar St, Blüdhaven
```
```
999 Cherry St, Keystone City
```
```
1000 Bamboo St, Smallville
```
```
1111 Maple Lane, Gotham City
```
```
2222 Elm Place, Metropolis
```
```
3333 Summer St, Starling City
```
```
4444 Winter Rd, Central City
```
```
5555 Willow Ave, National City
```
```
6666 Pine Blvd, Coast City
```
```
7777 Oak Dr, Atlantis
```
```
8888 Birch St, Wakanda
```
```
1010 Cypress St, Elms Town
```
```
2020 Maple Rd, Timber City
```
```
3030 Cedar St, Hill Valley
```
```
4040 Aspen Ave, Twin Peaks
```
```
5050 Chestnut Rd, Emerald City
```
```
6060 Pine Lane, Neverland
```
```
7070 Birch St, Gotham Valley
```
```
8080 Elm Blvd, Metropolis Heights
```
```
9090 Maple St, Riverdale
```
```
1010 Oak Ct, Springfield
```
```
2020 Cedar Way, Sky City
```
```
3030 Pine Hill, Forest Town
```
```
4040 Oak Road, Deckard City
```
```
6060 Redwood Lane, Frontier City
```
```
7070 Aspen Trail, Prairie Town
```
```
8080 Hobbiton Rd, Shire Town
```
```
9090 Mordor Ave, Shadow City
```
```
1111 Capitol Rd, Panem City
```
```
2222 District Ave, Seam Village
```
```
4444 Winterfell Way, North Kingdom
```
```
5555 Hobbiton Path, Shire District
```
```
6666 Rivendell Ct, Elven Realm
```
```
7777 Zion Blvd, Matrix City
```
```
8888 Network Ln, Code Valley
```
```
9999 Nostromo St, LV-426 Colony
```
```
1010 Sulaco Ave, Gateway Station
```
```
2323 Vulcan St, Spock City
```
```
4040 Casterly Rock Dr, Lannister City
```
```
3030 Dragonstone St, Westeros Isle
```
```
5050 Millennium Falcon Path, Corellia System
```
```
6060 Tatooine Circle, Outer Rim Territories
```
```
7070 Diagon Alley, Wizard Town
```
```
8080 Hogwarts St, Magic City
```
```
9090 Adventure Ave, Archaeologist City
```
```
1011 Temple St, Lost Kingdom
```
```
1112 Starfleet Headquarters, San Francisco
```
```
1213 Vulcan Academy, ShiKahr
```
```
1414 Jedi Temple, Coruscant
```
```
1515 Dagobah System, Outer Rim
```

| Invalid Lat/Lon | 
|---| 
```
Invalid Lat: 34.0522 Lon: -118.2437 for address: 456 Elm St, Springfield
```
```
Invalid Lat: 40.7128 Lon: -74.006 for address: 123 Main St, Springfield
```
```
Invalid Lat: 30.2672 Lon: -97.7431 for address: 777 Willow St, Coast City
```
```
Invalid Lat: -23.5505 Lon: -46.6333 for address: 5050 Spruce Street, Replicant Town
```
```
Invalid Lat: 51.1657 Lon: 10.4515 for address: 3333 Kings Landing Rd, Westeros
```
```
Invalid Lat: 45.4642 Lon: 9.19 for address: 1212 Enterprise Blvd, Starfleet HQ
```

