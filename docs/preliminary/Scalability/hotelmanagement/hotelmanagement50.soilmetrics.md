# Generation 1
```
-- Bookings
!new Booking('booking1')
!new Booking('booking2')
!new Booking('booking3')
!new Booking('booking4')
!new Booking('booking5')
!new Booking('booking6')
!new Booking('booking7')
!new Booking('booking8')

-- Assign attributes to Booking instances
!booking1.startDate := '2023-10-01'
!booking1.endDate := '2023-10-07'
!booking1.canceled := false
!booking1.bookingId := 101
!booking1.confirmed := true

!booking2.startDate := '2023-10-08'
!booking2.endDate := '2023-10-14'
!booking2.canceled := false
!booking2.bookingId := 102
!booking2.confirmed := true

!booking3.startDate := '2023-10-15'
!booking3.endDate := '2023-10-21'
!booking3.canceled := true
!booking3.bookingId := 103
!booking3.confirmed := false

!booking4.startDate := '2023-10-22'
!booking4.endDate := '2023-10-28'
!booking4.canceled := false
!booking4.bookingId := 104
!booking4.confirmed := true

!booking5.startDate := '2023-11-01'
!booking5.endDate := '2023-11-07'
!booking5.canceled := true
!booking5.bookingId := 105
!booking5.confirmed := false

!booking6.startDate := '2023-11-08'
!booking6.endDate := '2023-11-14'
!booking6.canceled := false
!booking6.bookingId := 106
!booking6.confirmed := true

!booking7.startDate := '2023-11-15'
!booking7.endDate := '2023-11-21'
!booking7.canceled := false
!booking7.bookingId := 107
!booking7.confirmed := true

!booking8.startDate := '2023-11-22'
!booking8.endDate := '2023-11-28'
!booking8.canceled := true
!booking8.bookingId := 108
!booking8.confirmed := false

-- Bills
!new Bill('bill1')
!new Bill('bill2')
!new Bill('bill3')
!new Bill('bill4')
!new Bill('bill5')
!new Bill('bill6')
!new Bill('bill7')
!new Bill('bill8')

-- Assign attributes to Bill instances
!bill1.price := 200.50
!bill1.billId := 201

!bill2.price := 350.75
!bill2.billId := 202

!bill3.price := 150.00
!bill3.billId := 203

!bill4.price := 400.99
!bill4.billId := 204

!bill5.price := 280.47
!bill5.billId := 205

!bill6.price := 320.80
!bill6.billId := 206

!bill7.price := 599.99
!bill7.billId := 207

!bill8.price := 750.00
!bill8.billId := 208

-- FreeRoomTypesDTO
!new FreeRoomTypesDTO('freeRoomType1')
!new FreeRoomTypesDTO('freeRoomType2')

-- Assign attributes to FreeRoomTypesDTO instances
!freeRoomType1.roomTypeDescription := 'Deluxe Room'
!freeRoomType1.numBeds := 2
!freeRoomType1.pricePerNight := 150.00
!freeRoomType1.numFreeRooms := 5

!freeRoomType2.roomTypeDescription := 'Single Room'
!freeRoomType2.numBeds := 1
!freeRoomType2.pricePerNight := 100.00
!freeRoomType2.numFreeRooms := 3

-- Customers
!new Customer('customer1')
!new Customer('customer2')
!new Customer('customer3')

-- Assign attributes to Customer instances
!customer1.firstName := 'John'
!customer1.lastName := 'Doe'

!customer2.firstName := 'Jane'
!customer2.lastName := 'Smith'

!customer3.firstName := 'Alice'
!customer3.lastName := 'Johnson'

-- RoomReservations
!new RoomReservation('roomReservation1')
!new RoomReservation('roomReservation2')
!new RoomReservation('roomReservation3')
!new RoomReservation('roomReservation4')
!new RoomReservation('roomReservation5')
!new RoomReservation('roomReservation6')
!new RoomReservation('roomReservation7')
!new RoomReservation('roomReservation8')
!new RoomReservation('roomReservation9')

-- Assign attributes to RoomReservation instances
!roomReservation1.checkInDate := '2023-10-01'
!roomReservation1.checkOutDate := '2023-10-07'

!roomReservation2.checkInDate := '2023-10-08'
!roomReservation2.checkOutDate := '2023-10-14'

!roomReservation3.checkInDate := '2023-10-15'
!roomReservation3.checkOutDate := '2023-10-21'

!roomReservation4.checkInDate := '2023-10-22'
!roomReservation4.checkOutDate := '2023-10-28'

!roomReservation5.checkInDate := '2023-11-01'
!roomReservation5.checkOutDate := '2023-11-07'

!roomReservation6.checkInDate := '2023-11-08'
!roomReservation6.checkOutDate := '2023-11-14'

!roomReservation7.checkInDate := '2023-11-15'
!roomReservation7.checkOutDate := '2023-11-21'

!roomReservation8.checkInDate := '2023-11-22'
!roomReservation8.checkOutDate := '2023-11-28'

!roomReservation9.checkInDate := '2023-12-01'
!roomReservation9.checkOutDate := '2023-12-07'

-- RoomExtras
!new RoomExtra('roomExtra1')
!new RoomExtra('roomExtra2')

-- Assign attributes to RoomExtra instances
!roomExtra1.price := 15.00
!roomExtra1.description := 'Breakfast'

!roomExtra2.price := 30.00
!roomExtra2.description := 'Spa Access'

-- Rooms
!new Room('room1')
!new Room('room2')
!new Room('room3')
!new Room('room4')
!new Room('room5')
!new Room('room6')
!new Room('room7')
!new Room('room8')
!new Room('room9')
!new Room('room10')

-- Assign attributes to Room instances
!room1.numBeds := 2
!room1.pricePerNight := 150.00
!room1.occupied := true
!room1.blocked := false
!room1.roomNumber := 101

!room2.numBeds := 1
!room2.pricePerNight := 100.00
!room2.occupied := false
!room2.blocked := false
!room2.roomNumber := 102

!room3.numBeds := 3
!room3.pricePerNight := 200.00
!room3.occupied := true
!room3.blocked := false
!room3.roomNumber := 103

!room4.numBeds := 2
!room4.pricePerNight := 150.00
!room4.occupied := false
!room4.blocked := true
!room4.roomNumber := 104

!room5.numBeds := 1
!room5.pricePerNight := 100.00
!room5.occupied := true
!room5.blocked := true
!room5.roomNumber := 105

!room6.numBeds := 4
!room6.pricePerNight := 250.00
!room6.occupied := false
!room6.blocked := false
!room6.roomNumber := 106

!room7.numBeds := 3
!room7.pricePerNight := 200.00
!room7.occupied := true
!room7.blocked := false
!room7.roomNumber := 107

!room8.numBeds := 2
!room8.pricePerNight := 150.00
!room8.occupied := false
!room8.blocked := false
!room8.roomNumber := 108

!room9.numBeds := 1
!room9.pricePerNight := 100.00
!room9.occupied := true
!room9.blocked := false
!room9.roomNumber := 109

!room10.numBeds := 2
!room10.pricePerNight := 150.00
!room10.occupied := false
!room10.blocked := false
!room10.roomNumber := 110

-- Associations
!insert (booking1, bill1) into BookingBill
!insert (booking2, bill2) into BookingBill
!insert (booking3, bill3) into BookingBill
!insert (booking4, bill4) into BookingBill
!insert (booking5, bill5) into BookingBill
!insert (booking6, bill6) into BookingBill
!insert (booking7, bill7) into BookingBill
!insert (booking8, bill8) into BookingBill

!insert(roomReservation1, room1) into RoomReservationRoom
!insert (roomReservation2, room2) into RoomReservationRoom
!insert (roomReservation3, room3) into RoomReservationRoom
!insert (roomReservation4, room4) into RoomReservationRoom
!insert (roomReservation5, room5) into RoomReservationRoom
!insert (roomReservation6, room6) into RoomReservationRoom
!insert (roomReservation7, room7) into RoomReservationRoom
!insert (roomReservation8, room8) into RoomReservationRoom
!insert (roomReservation9, room9) into RoomReservationRoom

!insert (roomReservation1, roomExtra1) into RoomReservationExtras
!insert (roomReservation2, roomExtra2) into RoomReservationExtras

!insert (booking1, customer1) into BookingCustomer
!insert (booking2, customer2) into BookingCustomer
!insert (booking3, customer3) into BookingCustomer

!insert (booking1, roomReservation1) into BookingRoomReservation
!insert (booking2, roomReservation2) into BookingRoomReservation
!insert (booking3, roomReservation3) into BookingRoomReservation
!insert (booking4, roomReservation4) into BookingRoomReservation
!insert (booking5, roomReservation5) into BookingRoomReservation
!insert (booking6, roomReservation6) into BookingRoomReservation
!insert (booking7, roomReservation7) into BookingRoomReservation
!insert (booking8, roomReservation8) into BookingRoomReservation
!insert (booking8, roomReservation9) into BookingRoomReservation

!insert (bill1, roomReservation1) into BillRoomReservation
!insert (bill2, roomReservation2) into BillRoomReservation
!insert (bill3, roomReservation3) into BillRoomReservation
!insert (bill4, roomReservation4) into BillRoomReservation
!insert (bill5, roomReservation5) into BillRoomReservation
!insert (bill6, roomReservation6) into BillRoomReservation
!insert (bill7, roomReservation7) into BillRoomReservation
!insert (bill8, roomReservation8) into BillRoomReservation

```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 223 | 0.00% |
| Multiplicities Errors | 7 | 38 | 18.42% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BillRoomReservation':
  Object `roomReservation9' of class `RoomReservation' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking7' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking8' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking5' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking6' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking4' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room10' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```

| HotelManagement | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| checkInDate >= startDate | 0 | 8 | 0.00% |
| checkOutDate <= endDate | 1 | 8 | 12.50% |

| Invalid checkOutDate <= endDate | 
|---| 
```
2023-12-07 !<= 2023-11-28
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
| Syntax Errors | 0 | 223 | 0.00% |
| Multiplicities Errors | 7 | 38 | 18.42% |
| Invariants Errors | 0 | 3 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `BillRoomReservation':
  Object `roomReservation9' of class `RoomReservation' is connected to 0 objects of class `Bill'
  at association end `bill' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking7' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking8' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking5' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking6' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `BookingCustomer':
  Object `booking4' of class `Booking' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RoomReservationRoom':
  Object `room10' of class `Room' is connected to 0 objects of class `RoomReservation'
  at association end `roomReservation' but the multiplicity is specified as `1'.
```

| HotelManagement | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| checkInDate >= startDate | 0 | 8 | 0.00% |
| checkOutDate <= endDate | 1 | 8 | 12.50% |

| Invalid checkOutDate <= endDate | 
|---| 
```
2023-12-07 !<= 2023-11-28
```

