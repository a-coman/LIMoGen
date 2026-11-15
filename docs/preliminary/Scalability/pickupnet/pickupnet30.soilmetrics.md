# Generation 1
```
!new Driver('driver1')
!driver1.id := 'D001'
!driver1.name := 'Alice'

!new Driver('driver2')
!driver2.id := 'D002'
!driver2.name := 'Bob'

!new Driver('driver3')
!driver3.id := 'D003'
!driver3.name := 'Charlie'

!new Shipment('shipment1')
!shipment1.id := 'S001'
!shipment1.status := #NEW

!new Shipment('shipment2')
!shipment2.id := 'S002'
!shipment2.status := #ASSIGNED

!new Shipment('shipment3')
!shipment3.id := 'S003'
!shipment3.status := #UNDERWAY

!new Address('address1')
!address1.text := '123 Main St'

!new Address('address2')
!address2.text := '456 Elm St'

!new Address('address3')
!address3.text := '789 Oak St'

!new GeoLocation('geo1')
!geo1.latitude := 40.7128
!geo1.longitude := -74.0060

!new GeoLocation('geo2')
!geo2.latitude := 34.0522
!geo2.longitude := -118.2437

!new GeoLocation('geo3')
!geo3.latitude := 37.7749
!geo3.longitude := -122.4194

!new Station('station1')

!new Customer('customer1')
!customer1.id := 'C001'
!customer1.name := 'Dave'
!customer1.twitterUserName := '@dave'

!new Customer('customer2')
!customer2.id := 'C002'
!customer2.name := 'Eva'
!customer2.twitterUserName := '@eva'

!new Customer('customer3')
!customer3.id := 'C003'
!customer3.name := 'Frank'
!customer3.twitterUserName := '@frank'

!insert (driver1, shipment1) into DriverShipment
!insert (driver2, shipment2) into DriverShipment

!insert (shipment1, address1) into ShipmentContainsPickUpAddress
!insert (shipment1, address2) into ShipmentContainsDeliveryAddress

!insert (shipment2, address2) into ShipmentContainsPickUpAddress
!insert (shipment2, address3) into ShipmentContainsDeliveryAddress

!insert (shipment3, address3) into ShipmentContainsPickUpAddress
!insert (shipment3, address1) into ShipmentContainsDeliveryAddress

!insert (address1, geo1) into AddressContainsGeoLocation
!insert (address2, geo2) into AddressContainsGeoLocation
!insert (address3, geo3) into AddressContainsGeoLocation

!insert (customer1, shipment1) into CustomerConsistsOfShipment
!insert (customer2, shipment2) into CustomerConsistsOfShipment
!insert (customer3, shipment3) into CustomerConsistsOfShipment

!insert (station1, customer1) into StationContainsCustomer
!insert (station1, customer2) into StationContainsCustomer
!insert (station1, customer3) into StationContainsCustomer

!insert (station1, shipment1) into StationShipment
!insert (station1, shipment2) into StationShipment
!insert (station1, shipment3) into StationShipment

!insert (station1, driver1) into StationContainsDriver
!insert (station1, driver2) into StationContainsDriver
!insert (station1, driver3) into StationContainsDriver
ç!new Driver('driver1')
!driver1.id := 'D001'
!driver1.name := 'Alice'

!new Driver('driver2')
!driver2.id := 'D002'
!driver2.name := 'Bob'

!new Driver('driver3')
!driver3.id := 'D003'
!driver3.name := 'Charlie'

!new Driver('driver4')
!driver4.id := 'D004'
!driver4.name := 'Diana'

!new Driver('driver5')
!driver5.id := 'D005'
!driver5.name := 'Eli'

!new Shipment('shipment1')
!shipment1.id := 'S001'
!shipment1.status := #NEW

!new Shipment('shipment2')
!shipment2.id := 'S002'
!shipment2.status := #ASSIGNED

!new Shipment('shipment3')
!shipment3.id := 'S003'
!shipment3.status := #UNDERWAY

!new Shipment('shipment4')
!shipment4.id := 'S004'
!shipment4.status := #DELIVERED

!new Shipment('shipment5')
!shipment5.id := 'S005'
!shipment5.status := #NEW

!new Shipment('shipment6')
!shipment6.id := 'S006'
!shipment6.status := #ASSIGNED

!new Address('address1')
!address1.text := '123 Main St'

!new Address('address2')
!address2.text := '456 Elm St'

!new Address('address3')
!address3.text := '789 Oak St'

!new Address('address4')
!address4.text := '987 Pine St'

!new GeoLocation('geo1')
!geo1.latitude := 40.7128
!geo1.longitude := -74.0060

!new GeoLocation('geo2')
!geo2.latitude := 34.0522
!geo2.longitude := -118.2437

!new GeoLocation('geo3')
!geo3.latitude := 37.7749
!geo3.longitude := -122.4194

!new GeoLocation('geo4')
!geo4.latitude := 51.5074
!geo4.longitude := -0.1278

!new Station('station1')

!new Station('station2')

!new Customer('customer1')
!customer1.id := 'C001'
!customer1.name := 'Dave'
!customer1.twitterUserName := '@dave'

!new Customer('customer2')
!customer2.id := 'C002'
!customer2.name := 'Eva'
!customer2.twitterUserName := '@eva'

!new Customer('customer3')
!customer3.id := 'C003'
!customer3.name := 'Frank'
!customer3.twitterUserName := '@frank'

!new Customer('customer4')
!customer4.id := 'C004'
!customer4.name := 'Grace'
!customer4.twitterUserName := '@grace'

!insert (driver1, shipment1) into DriverShipment
!insert (driver2, shipment2) into DriverShipment

!insert (shipment1, address1) into ShipmentContainsPickUpAddress
!insert (shipment1, address2) into ShipmentContainsDeliveryAddress

!insert (shipment2, address2) into ShipmentContainsPickUpAddress
!insert (shipment2, address3) into ShipmentContainsDeliveryAddress

!insert (shipment3, address3) into ShipmentContainsPickUpAddress
!insert (shipment3, address4) into ShipmentContainsDeliveryAddress

!insert (address1, geo1) into AddressContainsGeoLocation
!insert (address2, geo2) into AddressContainsGeoLocation
!insert (address3, geo3) into AddressContainsGeoLocation
!insert (address4, geo4) into AddressContainsGeoLocation

!insert (customer1, shipment1) into CustomerConsistsOfShipment
!insert (customer2, shipment2) into CustomerConsistsOfShipment
!insert (customer3, shipment3) into CustomerConsistsOfShipment
!insert (customer4, shipment4) into CustomerConsistsOfShipment

!insert (station1, customer1) into StationContainsCustomer
!insert (station1, customer2) into StationContainsCustomer
!insert (station1, customer3) into StationContainsCustomer
!insert (station1, customer4) into StationContainsCustomer

!insert (station1, shipment1) into StationShipment
!insert (station1, shipment2) into StationShipment
!insert (station1, shipment3) into StationShipment
!insert (station2, shipment4) into StationShipment

!insert (station1, driver1) into StationContainsDriver
!insert (station1, driver2) into StationContainsDriver
!insert (station2, driver3) into StationContainsDriver
!insert (station2, driver4) into StationContainsDriver

```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 37 | 168 | 22.02% |
| Multiplicities Errors | 13 | 51 | 25.49% |
| Invariants Errors | 0 | 4 | 0.00% |

| Syntax Errors | 
|---| 
```
Error: Unknown command `ç!new Driver('driver1')'. Try `help'.
```
```
Error: An object with name `driver2' already exists.
```
```
Error: An object with name `driver3' already exists.
```
```
Error: An object with name `shipment1' already exists.
```
```
Error: An object with name `shipment2' already exists.
```
```
Error: An object with name `shipment3' already exists.
```
```
Error: An object with name `address1' already exists.
```
```
Error: An object with name `address2' already exists.
```
```
Error: An object with name `address3' already exists.
```
```
Error: An object with name `geo1' already exists.
```
```
Error: An object with name `geo2' already exists.
```
```
Error: An object with name `geo3' already exists.
```
```
Error: An object with name `station1' already exists.
```
```
Error: An object with name `customer1' already exists.
```
```
Error: An object with name `customer2' already exists.
```
```
Error: An object with name `customer3' already exists.
```
```
Error: Link `DriverShipment' between (driver1,shipment1) already exist.
```
```
Error: Link `DriverShipment' between (driver2,shipment2) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment1,address1) already exist.
```
```
Error: Link `ShipmentContainsDeliveryAddress' between (shipment1,address2) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment2,address2) already exist.
```
```
Error: Link `ShipmentContainsDeliveryAddress' between (shipment2,address3) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment3,address3) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address1,geo1) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address2,geo2) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address3,geo3) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer1,shipment1) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer2,shipment2) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer3,shipment3) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer1) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer2) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer3) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment1) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment2) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment3) already exist.
```
```
Error: Link `StationContainsDriver' between (station1,driver1) already exist.
```
```
Error: Link `StationContainsDriver' between (station1,driver2) already exist.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment3' of class `Shipment' is connected to 2 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment4' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment4' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationContainsDriver':
  Object `driver5' of class `Driver' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationContainsDriver':
  Object `driver3' of class `Driver' is connected to 2 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```

| PickupNet | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Address | 4 | 4 | 100.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 2 | 7 | 28.57% |

| Invalid Addresses | 
|---| 
```
789 Oak St
```
```
456 Elm St
```
```
123 Main St
```
```
987 Pine St
```

| Invalid Twitters | 
|---| 
```
@eva
```
```
@eva
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | pickupnet | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 37 | 168 | 22.02% |
| Multiplicities Errors | 13 | 51 | 25.49% |
| Invariants Errors | 0 | 4 | 0.00% |

| Syntax Errors | 
|---| 
```
Error: Unknown command `ç!new Driver('driver1')'. Try `help'.
```
```
Error: An object with name `driver2' already exists.
```
```
Error: An object with name `driver3' already exists.
```
```
Error: An object with name `shipment1' already exists.
```
```
Error: An object with name `shipment2' already exists.
```
```
Error: An object with name `shipment3' already exists.
```
```
Error: An object with name `address1' already exists.
```
```
Error: An object with name `address2' already exists.
```
```
Error: An object with name `address3' already exists.
```
```
Error: An object with name `geo1' already exists.
```
```
Error: An object with name `geo2' already exists.
```
```
Error: An object with name `geo3' already exists.
```
```
Error: An object with name `station1' already exists.
```
```
Error: An object with name `customer1' already exists.
```
```
Error: An object with name `customer2' already exists.
```
```
Error: An object with name `customer3' already exists.
```
```
Error: Link `DriverShipment' between (driver1,shipment1) already exist.
```
```
Error: Link `DriverShipment' between (driver2,shipment2) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment1,address1) already exist.
```
```
Error: Link `ShipmentContainsDeliveryAddress' between (shipment1,address2) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment2,address2) already exist.
```
```
Error: Link `ShipmentContainsDeliveryAddress' between (shipment2,address3) already exist.
```
```
Error: Link `ShipmentContainsPickUpAddress' between (shipment3,address3) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address1,geo1) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address2,geo2) already exist.
```
```
Error: Link `AddressContainsGeoLocation' between (address3,geo3) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer1,shipment1) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer2,shipment2) already exist.
```
```
Error: Link `CustomerConsistsOfShipment' between (customer3,shipment3) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer1) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer2) already exist.
```
```
Error: Link `StationContainsCustomer' between (station1,customer3) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment1) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment2) already exist.
```
```
Error: Link `StationShipment' between (station1,shipment3) already exist.
```
```
Error: Link `StationContainsDriver' between (station1,driver1) already exist.
```
```
Error: Link `StationContainsDriver' between (station1,driver2) already exist.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `CustomerConsistsOfShipment':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Customer'
  at association end `orderer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment3' of class `Shipment' is connected to 2 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment4' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsDeliveryAddress':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `shipToAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment4' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `ShipmentContainsPickUpAddress':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Address'
  at association end `pickUpAddress' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationContainsDriver':
  Object `driver5' of class `Driver' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationContainsDriver':
  Object `driver3' of class `Driver' is connected to 2 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment6' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `StationShipment':
  Object `shipment5' of class `Shipment' is connected to 0 objects of class `Station'
  at association end `station' but the multiplicity is specified as `1'.
```

| PickupNet | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Address | 4 | 4 | 100.00% |
| Lat/Lon (out of valid addresses) | 0 | 0 | 0.00% |
| Twitter | 2 | 7 | 28.57% |

| Invalid Addresses | 
|---| 
```
789 Oak St
```
```
456 Elm St
```
```
123 Main St
```
```
987 Pine St
```

| Invalid Twitters | 
|---| 
```
@eva
```
```
@eva
```

