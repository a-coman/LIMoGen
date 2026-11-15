# Generation 1
```
!new Booking('booking1')
!booking1.startDate := '2023-10-01'
!booking1.endDate := '2023-10-05'
!booking1.canceled := false
!booking1.bookingId := 1001
!booking1.confirmed := true

!new Booking('booking2')
!booking2.startDate := '2023-10-10'
!booking2.endDate := '2023-10-15'
!booking2.canceled := true
!booking2.bookingId := 1002
!booking2.confirmed := false

!new Booking('booking3')
!booking3.startDate := '2023-10-20'
!booking3.endDate := '2023-10-25'
!booking3.canceled := false
!booking3.bookingId := 1003
!booking3.confirmed := true

!new Bill('bill1')
!bill1.price := 500.0
!bill1.billId := 2001

!new Bill('bill2')
!bill2.price := 300.5
!bill2.billId := 2002

!new FreeRoomTypesDTO('roomType1')
!roomType1.roomTypeDescription := 'Single'
!roomType1.numBeds := 1
!roomType1.pricePerNight := 100.0
!roomType1.numFreeRooms := 5

!new FreeRoomTypesDTO('roomType2')
!roomType2.roomTypeDescription := 'Double'
!roomType2.numBeds := 2
!roomType2.pricePerNight := 150.0
!roomType2.numFreeRooms := 2

!new Customer('customer1')
!customer1.firstName := 'John'
!customer1.lastName := 'Doe'

!new Customer('customer2')
!customer2.firstName := 'Jane'
!customer2.lastName := 'Smith'

!new RoomReservation('reservation1')
!reservation1.checkInDate := '2023-10-01'
!reservation1.checkOutDate := '2023-10-05'

!new RoomReservation('reservation2')
!reservation2.checkInDate := '2023-10-10'
!reservation2.checkOutDate := '2023-10-12'

!new RoomExtra('extra1')
!extra1.price := 20.0
!extra1.description := 'Breakfast'

!new RoomExtra('extra2')
!extra2.price := 15.0
!extra2.description := 'Parking'

!new Room('room1')
!room1.numBeds := 1
!room1.pricePerNight := 120.0
!room1.occupied := true
!room1.blocked := false
!room1.roomNumber := 101

!new Room('room2')
!room2.numBeds := 2
!room2.pricePerNight := 180.0
!room2.occupied := false
!room2.blocked := true
!room2.roomNumber := 102

!new Room('room3')
!room3.numBeds := 1
!room3.pricePerNight := 100.0
!room3.occupied := false
!room3.blocked := false
!room3.roomNumber := 103

!new Room('room4')
!room4.numBeds := 3
!room4.pricePerNight := 220.0
!room4.occupied := false
!room4.blocked := false
!room4.roomNumber := 104

!new Room('room5')
!room5.numBeds := 2
!room5.pricePerNight := 150.0
!room5.occupied := false
!room5.blocked := false
!room5.roomNumber := 105

!insert (booking1, bill1) into BookingBill
!insert (booking2, bill2) into BookingBill

!insert (booking1, customer1) into BookingCustomer
!insert (booking2, customer2) into BookingCustomer

!insert (booking1, reservation1) into BookingRoomReservation
!insert (booking2, reservation2) into BookingRoomReservation

!insert (reservation1, extra1) into RoomReservationExtras
!insert (reservation2, extra2) into RoomReservationExtras

!insert (reservation1, room1) into RoomReservationRoom
!insert (reservation2, room2) into RoomReservationRoom

!insert (bill1, reservation1) into BillRoomReservation
!insert (bill2, reservation2) into BillRoomReservation

!new Booking('booking3')
!booking3.startDate := '2023-10-30'
!booking3.endDate := '2023-11-04'
!booking3.canceled := false
!booking3.bookingId := 1004
!booking3.confirmed := true

!new Booking('booking4')
!booking4.startDate := '2023-11-15'
!booking4.endDate := '2023-11-20'
!booking4.canceled := false
!booking4.bookingId := 1005
!booking4.confirmed := true

!new Bill('bill3')
!bill3.price := 750.0
!bill3.billId := 2003

!new FreeRoomTypesDTO('roomType3')
!roomType3.roomTypeDescription := 'Suite'
!roomType3.numBeds := 3
!roomType3.pricePerNight := 250.0
!roomType3.numFreeRooms := 1

!new Customer('customer3')
!customer3.firstName := 'Alice'
!customer3.lastName := 'Johnson'

!new RoomReservation('reservation3')
!reservation3.checkInDate := '2023-11-15'
!reservation3.checkOutDate := '2023-11-20'

!new RoomExtra('extra3')
!extra3.price := 30.0
!extra3.description := 'Room Service'

!new RoomExtra('extra4')
!extra4.price := 10.0
!extra4.description := 'Wi-Fi'

!new Room('room6')
!room6.numBeds := 1
!room6.pricePerNight := 110.0
!room6.occupied := true
!room6.blocked := false
!room6.roomNumber := 106

!new Room('room7')
!room7.numBeds := 2
!room7.pricePerNight := 170.0
!room7.occupied := true
!room7.blocked := false
!room7.roomNumber := 107

!new Room('room8')
!room8.numBeds := 3
!room8.pricePerNight := 250.0
!room8.occupied := false
!room8.blocked := false
!room8.roomNumber := 108

!insert (booking3, bill3) into BookingBill
!insert (booking4, bill3) into BookingBill

!insert (booking3, customer3) into BookingCustomer
!insert (booking4, customer3) into BookingCustomer

!insert (booking3, reservation3) into BookingRoomReservation
!insert (booking4, reservation3) into BookingRoomReservation

!insert (reservation3, extra3) into RoomReservationExtras
!insert (reservation3, extra4) into RoomReservationExtras

!insert (reservation3, room6) into RoomReservationRoom
!insert (reservation3, room7) into RoomReservationRoom
!insert (reservation3, room8) into RoomReservationRoom

!insert (bill3, reservation3) into BillRoomReservation
```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 156 | 0.00% |
| Multiplicities Errors | 6 | 24 | 25.00% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BookingBill':
  Object `bill3' of class `Bill' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `customer3' of class `Customer' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingRoomReservation':
  Object `reservation3' of class `RoomReservation' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room5' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room3' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room4' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```

| HotelManagement | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| checkInDate >= startDate | 0 | 4 | 0.00% |
| checkOutDate <= endDate | 1 | 4 | 25.00% |

| Invalid checkOutDate <= endDate | 
|---| 
```
2023-11-20 !<= 2023-11-04
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | hotelmanagement | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 156 | 0.00% |
| Multiplicities Errors | 6 | 24 | 25.00% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BookingBill':
  Object `bill3' of class `Bill' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `customer3' of class `Customer' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingRoomReservation':
  Object `reservation3' of class `RoomReservation' is connected to 2 objects of class `Booking'
  at association end `booking' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room5' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room3' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room4' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```

| HotelManagement | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| checkInDate >= startDate | 0 | 4 | 0.00% |
| checkOutDate <= endDate | 1 | 4 | 25.00% |

| Invalid checkOutDate <= endDate | 
|---| 
```
2023-11-20 !<= 2023-11-04
```

