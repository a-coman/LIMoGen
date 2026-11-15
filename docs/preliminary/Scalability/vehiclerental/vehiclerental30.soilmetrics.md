# Generation 1
```
-- Creating RentalOffices
!new RentalOffice('office1')
!office1.name := 'Downtown Depot'
!office1.number := 101
!office1.address := '123 Main St, CA'

!new RentalOffice('office2')
!office2.name := 'Airport Hub'
!office2.number := 102
!office2.address := '456 Airport Rd, FL'

-- Creating Vehicles
!new Vehicle('vehicle1')
!vehicle1.id := 1
!vehicle1.registrationState := #CA
!vehicle1.licensePlateNumber := 'ABC123'
!vehicle1.vehicleTypeCode := #TRUCK
!vehicle1.registrationLastMaintenanceDate := Date('2023-01-01')
!vehicle1.expirationDate := Date('2024-01-01')

!new Vehicle('vehicle2')
!vehicle2.id := 2
!vehicle2.registrationState := #FL
!vehicle2.licensePlateNumber := 'XYZ789'
!vehicle2.vehicleTypeCode := #TRUCK24
!vehicle2.registrationLastMaintenanceDate := Date('2023-02-15')
!vehicle2.expirationDate := Date('2024-02-15')

!new Truck('truck1')
!truck1.id := 3
!truck1.registrationState := #AL
!truck1.licensePlateNumber := 'TRK001'
!truck1.vehicleTypeCode := #TRUCK10
!truck1.registrationLastMaintenanceDate := Date('2023-03-05')
!truck1.expirationDate := Date('2024-03-05')
!truck1.odometerReading := 15000
!truck1.gasTankCapacity := 50.0
!truck1.workingRadio := true
!truck1.mileage := 10

-- Creating RentalAgreements
!new RentalAgreement('agreement1')
!agreement1.number := 201
!agreement1.rentalDate := Date('2023-04-01')
!agreement1.anticipatedDuration := 7
!agreement1.depositPaid := 100.0
!agreement1.quotedDailyRate := 25.0
!agreement1.quotedRatePerMile := 0.5

!new RentalAgreement('agreement2')
!agreement2.number := 202
!agreement2.rentalDate := Date('2023-04-05')
!agreement2.anticipatedDuration := 3
!agreement2.depositPaid := 50.0
!agreement2.quotedDailyRate := 30.0
!agreement2.quotedRatePerMile := 0.6

-- Creating Customers
!new Individual('customer1')
!customer1.name := 'John Doe'
!customer1.address := '789 Park Ave, AL'
!customer1.poorRisk := false
!customer1.homePhone := '555-1234'
!customer1.driverLicenseState := #AL
!customer1.driverLicenseNumber := 123456789
!customer1.driverLicenseExpirationDate := Date('2025-06-30')

!new Individual('customer2')
!customer2.name := 'Jane Smith'
!customer2.address := '321 Elm St, FL'
!customer2.poorRisk := true
!customer2.homePhone := '555-5678'
!customer2.driverLicenseState := #FL
!customer2.driverLicenseNumber := 987654321
!customer2.driverLicenseExpirationDate := Date('2026-12-31')

!new Company('company1')
!company1.name := 'Tech Corp'
!company1.address := '456 Silicon Blvd, CA'
!company1.poorRisk := false
!company1.idNumber := 111223

-- Associations
!insert (office1, vehicle1) into RentalOfficeVehicle
!insert (office2, vehicle2) into RentalOfficeVehicle
!insert (office1, truck1) into RentalOfficeVehicle

!insert (office1, agreement1) into RentalOfficeRentalAgreementOrigin
!insert (office2, agreement2) into RentalOfficeRentalAgreementOrigin

!insert (office2, agreement1) into RentalOfficeRentalAgreementDrop
!insert (office1, agreement2) into RentalOfficeRentalAgreementDrop

!insert (agreement1, vehicle1) into RentalAgreementVehicle
!insert (agreement2, vehicle2) into RentalAgreementVehicle

!insert (agreement1, customer1) into RentalAgreementCustomer
!insert (agreement2, company1) into RentalAgreementCustomer

-- More entities to comply with the requirement
-- Creating additional Rentals, Customers, and Vehicles

!new RentalAgreement('agreement3')
!agreement3.number := 203
!agreement3.rentalDate := Date('2023-01-15')
!agreement3.anticipatedDuration := 5
!agreement3.depositPaid := 120.0
!agreement3.quotedDailyRate := 35.0
!agreement3.quotedRatePerMile := 0.7

!new Individual('customer3')
!customer3.name := 'Sam Wilson'
!customer3.address := '101 Maple Dr, CO'
!customer3.poorRisk := false
!customer3.homePhone := '555-1212'
!customer3.driverLicenseState := #CO
!customer3.driverLicenseNumber := 111223333
!customer3.driverLicenseExpirationDate := Date('2028-08-15')

!new Truck('truck2')
!truck2.id := 4
!truck2.registrationState := #AK
!truck2.licensePlateNumber := 'TRK002'
!truck2.vehicleTypeCode := #COVERED_TRAILER
!truck2.registrationLastMaintenanceDate := Date('2023-06-10')
!truck2.expirationDate := Date('2024-06-10')
!truck2.odometerReading := 20000
!truck2.gasTankCapacity := 60.0
!truck2.workingRadio := false
!truck2.mileage := 15

!insert (office2, agreement3) into RentalOfficeRentalAgreementOrigin

!insert (office1, truck2) into RentalOfficeVehicle

!insert (agreement3, truck2) into RentalAgreementVehicle

!insert (agreement3, customer3) into RentalAgreementCustomer

-- Creating more Vehicles
!new Vehicle('vehicle3')
!vehicle3.id := 5
!vehicle3.registrationState := #AZ
!vehicle3.licensePlateNumber := 'JKL456'
!vehicle3.vehicleTypeCode := #OPEN_TRAILER
!vehicle3.registrationLastMaintenanceDate := Date('2023-07-05')
!vehicle3.expirationDate := Date('2024-07-05')

!new Truck('truck3')
!truck3.id := 6
!truck3.registrationState := #DE
!truck3.licensePlateNumber := 'TRK003'
!truck3.vehicleTypeCode := #TRUCK
!truck3.registrationLastMaintenanceDate := Date('2023-08-01')
!truck3.expirationDate := Date('2024-08-01')
!truck3.odometerReading := 25000
!truck3.gasTankCapacity := 55.0
!truck3.workingRadio := true
!truck3.mileage := 12

-- Creating more RentalAgreements
!new RentalAgreement('agreement4')
!agreement4.number := 204
!agreement4.rentalDate := Date('2023-05-10')
!agreement4.anticipatedDuration := 10
!agreement4.depositPaid := 90.0
!agreement4.quotedDailyRate := 20.0
!agreement4.quotedRatePerMile := 0.4

!new RentalAgreement('agreement5')
!agreement5.number := 205
!agreement5.rentalDate := Date('2023-06-20')
!agreement5.anticipatedDuration := 8
!agreement5.depositPaid := 110.0
!agreement5.quotedDailyRate := 40.0
!agreement5.quotedRatePerMile := 0.8

-- Creating more Customers
!new Individual('customer4')
!customer4.name := 'Alice Green'
!customer4.address := '55 Pine Ln, CT'
!customer4.poorRisk := true
!customer4.homePhone := '555-8765'
!customer4.driverLicenseState := #CT
!customer4.driverLicenseNumber := 246812345
!customer4.driverLicenseExpirationDate := Date('2027-11-30')

!new Company('company2')
!company2.name := 'Logistics Ltd'
!company2.address := '789 Cypress St, AZ'
!company2.poorRisk := false
!company2.idNumber := 555667

-- Creating Associations
!insert (office2, vehicle3) into RentalOfficeVehicle

!insert (office1, truck3) into RentalOfficeVehicle

!insert (office1, agreement4) into RentalOfficeRentalAgreementOrigin
!insert (office2, agreement5) into RentalOfficeRentalAgreementOrigin

!insert (office2, agreement4) into RentalOfficeRentalAgreementDrop
!insert (office1, agreement5) into RentalOfficeRentalAgreementDrop

!insert (agreement4, vehicle3) into RentalAgreementVehicle
!insert (agreement5, truck3) into RentalAgreementVehicle

!insert (agreement4, customer4) into RentalAgreementCustomer
!insert (agreement5, company2) into RentalAgreementCustomer

-- Creating more Vehicles
!new Vehicle('vehicle4')
!vehicle4.id := 7
!vehicle4.registrationState := #CO
!vehicle4.licensePlateNumber := 'LMN789'
!vehicle4.vehicleTypeCode := #TRUCK24
!vehicle4.registrationLastMaintenanceDate := Date('2023-09-15')
!vehicle4.expirationDate := Date('2024-09-15')

!new Truck('truck4')
!truck4.id := 8
!truck4.registrationState := #CT
!truck4.licensePlateNumber := 'TRK004'
!truck4.vehicleTypeCode := #TRUCK10
!truck4.registrationLastMaintenanceDate := Date('2023-10-01')
!truck4.expirationDate := Date('2024-10-01')
!truck4.odometerReading := 30000
!truck4.gasTankCapacity := 70.0
!truck4.workingRadio := false
!truck4.mileage := 14

-- Creating more RentalAgreements
!new RentalAgreement('agreement6')
!agreement6.number := 206
!agreement6.rentalDate := Date('2023-08-25')
!agreement6.anticipatedDuration := 2
!agreement6.depositPaid := 75.0
!agreement6.quotedDailyRate := 45.0
!agreement6.quotedRatePerMile := 0.9

!new RentalAgreement('agreement7')
!agreement7.number := 207
!agreement7.rentalDate := Date('2023-07-30')
!agreement7.anticipatedDuration := 4
!agreement7.depositPaid := 65.0
!agreement7.quotedDailyRate := 22.0
!agreement7.quotedRatePerMile := 0.3

-- Creating more Customers
!new Individual('customer5')
!customer5.name := 'Bob Brown'
!customer5.address := '303 Aspen Ct, FL'
!customer5.poorRisk := false
!customer5.homePhone := '555-4567'
!customer5.driverLicenseState := #FL
!customer5.driverLicenseNumber := 777888999
!customer5.driverLicenseExpirationDate := Date('2029-04-25')

-- Associations
!insert (office1, vehicle4) into RentalOfficeVehicle
!insert (office2, truck4) into RentalOfficeVehicle

!insert (office2, agreement6) into RentalOfficeRentalAgreementOrigin
!insert (office1, agreement7) into RentalOfficeRentalAgreementOrigin

!insert (office1, agreement6) into RentalOfficeRentalAgreementDrop
!insert (office2, agreement7) into RentalOfficeRentalAgreementDrop

!insert (agreement6, vehicle4) into RentalAgreementVehicle
!insert (agreement7, truck4) into RentalAgreementVehicle

!insert (agreement6, customer5) into RentalAgreementCustomer

-- Creating more Vehicles
!new Vehicle('vehicle5')
!vehicle5.id := 9
!vehicle5.registrationState := #DE
!vehicle5.licensePlateNumber := 'OPR123'
!vehicle5.vehicleTypeCode := #COVERED_TRAILER
!vehicle5.registrationLastMaintenanceDate := Date('2023-11-20')
!vehicle5.expirationDate := Date('2024-11-20')

-- Creating more RentalAgreements
!new RentalAgreement('agreement8')
!agreement8.number := 208
!agreement8.rentalDate := Date('2023-11-01')
!agreement8.anticipatedDuration := 6
!agreement8.depositPaid := 80.0
!agreement8.quotedDailyRate := 50.0
!agreement8.quotedRatePerMile := 0.75

-- Creating more Customers
!new Individual('customer6')
!customer6.name := 'Charlie Johnson'
!customer6.address := '809 Oak St, AK'
!customer6.poorRisk := true
!customer6.homePhone := '555-2233'
!customer6.driverLicenseState := #AK
!customer6.driverLicenseNumber := 333444555
!customer6.driverLicenseExpirationDate := Date('2028-05-01')

!new Company('company3')
!company3.name := 'Freight Masters'
!company3.address := '222 Transport Way, FL'
!company3.poorRisk := false
!company3.idNumber := 998877

-- Associations
!insert (office1, vehicle5) into RentalOfficeVehicle

!insert (office2, agreement8) into RentalOfficeRentalAgreementOrigin

!insert (office1, agreement8) into RentalOfficeRentalAgreementDrop

!insert (agreement8, vehicle5) into RentalAgreementVehicle

!insert (agreement8, customer6) into RentalAgreementCustomer


```
## Generation 1 summary
| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 245 | 0.00% |
| Multiplicities Errors | 2 | 39 | 5.13% |
| Invariants Errors | 0 | 5 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalAgreementCustomer':
  Object `agreement7' of class `RentalAgreement' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `agreement3' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Addresses | 4 | 11 | 36.36% |
| License Plates | 0 | 9 | 0.00% |
| Home Phones | 0 | 6 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Silicon Blvd, CA
```
```
303 Aspen Ct, FL
```
```
809 Oak St, AK
```
```
222 Transport Way, FL
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | null | 
| Type |  | 
| System | vehiclerental | 
| Number of generations | 1 | 

| General | Errors | Total | Failure (%) | 
|---|---|---|---| 
| Syntax Errors | 0 | 245 | 0.00% |
| Multiplicities Errors | 2 | 39 | 5.13% |
| Invariants Errors | 0 | 5 | 0.00% |

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalAgreementCustomer':
  Object `agreement7' of class `RentalAgreement' is connected to 0 objects of class `Customer'
  at association end `customer' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `agreement3' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Invalid | Total | Failure (%) | 
|---|---|---|---| 
| Addresses | 4 | 11 | 36.36% |
| License Plates | 0 | 9 | 0.00% |
| Home Phones | 0 | 6 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Silicon Blvd, CA
```
```
303 Aspen Ct, FL
```
```
809 Oak St, AK
```
```
222 Transport Way, FL
```

