# Generation 1
```
!new RentalOffice('rentalOffice1')
!rentalOffice1.name := 'Downtown Rentals'
!rentalOffice1.number := 101
!rentalOffice1.address := '123 Main St, CA'

!new RentalOffice('rentalOffice2')
!rentalOffice2.name := 'Beach Rentals'
!rentalOffice2.number := 202
!rentalOffice2.address := '456 Ocean Dr, FL'

!new Vehicle('vehicle1')
!vehicle1.id := 1001
!vehicle1.registrationState := #CA
!vehicle1.licensePlateNumber := 'CA1234'
!vehicle1.vehicleTypeCode := #TRUCK
!vehicle1.registrationLastMaintenanceDate := Date('2023-01-01')
!vehicle1.expirationDate := Date('2024-01-01')

!new Vehicle('vehicle2')
!vehicle2.id := 1002
!vehicle2.registrationState := #FL
!vehicle2.licensePlateNumber := 'FL5678'
!vehicle2.vehicleTypeCode := #COVERED_TRAILER
!vehicle2.registrationLastMaintenanceDate := Date('2023-05-01')
!vehicle2.expirationDate := Date('2024-05-01')

!new Truck('truck1')
!truck1.id := 2001
!truck1.registrationState := #AZ
!truck1.licensePlateNumber := 'AZ9012'
!truck1.vehicleTypeCode := #TRUCK24
!truck1.registrationLastMaintenanceDate := Date('2023-03-01')
!truck1.expirationDate := Date('2024-03-01')
!truck1.odometerReading := 50000
!truck1.gasTankCapacity := 35.0
!truck1.workingRadio := true
!truck1.mileage := 12

!new Truck('truck2')
!truck2.id := 2002
!truck2.registrationState := #CA
!truck2.licensePlateNumber := 'CA3456'
!truck2.vehicleTypeCode := #TRUCK10
!truck2.registrationLastMaintenanceDate := Date('2023-06-01')
!truck2.expirationDate := Date('2024-06-01')
!truck2.odometerReading := 30000
!truck2.gasTankCapacity := 40.0
!truck2.workingRadio := false
!truck2.mileage := 15

!new RentalAgreement('rentalAgreement1')
!rentalAgreement1.number := 5001
!rentalAgreement1.rentalDate := Date('2023-09-01')
!rentalAgreement1.anticipatedDuration := 3
!rentalAgreement1.depositPaid := 100.0
!rentalAgreement1.quotedDailyRate := 50.0
!rentalAgreement1.quotedRatePerMile := 0.5

!new RentalAgreement('rentalAgreement2')
!rentalAgreement2.number := 5002
!rentalAgreement2.rentalDate := Date('2023-10-01')
!rentalAgreement2.anticipatedDuration := 5
!rentalAgreement2.depositPaid := 150.0
!rentalAgreement2.quotedDailyRate := 55.0
!rentalAgreement2.quotedRatePerMile := 0.4

!new Individual('individual1')
!individual1.name := 'John Doe'
!individual1.address := '789 Elm St, CO'
!individual1.poorRisk := false
!individual1.homePhone := '303-555-0123'
!individual1.driverLicenseState := #CO
!individual1.driverLicenseNumber := 987654321
!individual1.driverLicenseExpirationDate := Date('2025-02-15')

!new Individual('individual2')
!individual2.name := 'Jane Smith'
!individual2.address := '101 Maple Ave, FL'
!individual2.poorRisk := true
!individual2.homePhone := '305-555-0456'
!individual2.driverLicenseState := #FL
!individual2.driverLicenseNumber := 123456789
!individual2.driverLicenseExpirationDate := Date('2026-07-20')

!new Company('company1')
!company1.name := 'TechCorp'
!company1.address := '202 Silicon St, CA'
!company1.poorRisk := false
!company1.idNumber := 111222333

!insert (rentalOffice1, vehicle1) into RentalOfficeVehicle
!insert (rentalOffice1, truck1) into RentalOfficeVehicle
!insert (rentalOffice2, vehicle2) into RentalOfficeVehicle
!insert (rentalOffice2, truck2) into RentalOfficeVehicle

!insert (rentalOffice1, rentalAgreement1) into RentalOfficeRentalAgreementOrigin
!insert (rentalOffice2, rentalAgreement2) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice1, rentalAgreement2) into RentalOfficeRentalAgreementDrop
!insert (rentalOffice2, rentalAgreement1) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement1, vehicle1) into RentalAgreementVehicle
!insert (rentalAgreement2, truck1) into RentalAgreementVehicle

!insert (rentalAgreement1, individual1) into RentalAgreementCustomer
!insert (rentalAgreement2, company1) into RentalAgreementCustomer
```
## Generation 1 summary
| General | Value | 
|---|---| 
| Syntax Errors | 0 | 
| Multiplicities Errors | 0 | 
| Invariants Errors | 0 | 

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 4 | 5 | 80.00% |
| License Plates | 4 | 4 | 100.00% |
| Home Phones | 2 | 2 | 100.00% |

| Invalid Addresses | 
|---| 
```
202 Silicon St, CA
```

# Generation 2
```
!new RentalOffice('rentalOffice3')
!rentalOffice3.name := 'Mountain Rentals'
!rentalOffice3.number := 303
!rentalOffice3.address := '789 Alpine Rd, CO'

!new Vehicle('vehicle3')
!vehicle3.id := 1003
!vehicle3.registrationState := #CO
!vehicle3.licensePlateNumber := 'CO4567'
!vehicle3.vehicleTypeCode := #OPEN_TRAILER
!vehicle3.registrationLastMaintenanceDate := Date('2023-02-01')
!vehicle3.expirationDate := Date('2024-02-01')

!new Truck('truck3')
!truck3.id := 2003
!truck3.registrationState := #AK
!truck3.licensePlateNumber := 'AK1234'
!truck3.vehicleTypeCode := #TRUCK
!truck3.registrationLastMaintenanceDate := Date('2023-07-01')
!truck3.expirationDate := Date('2024-07-01')
!truck3.odometerReading := 75000
!truck3.gasTankCapacity := 45.0
!truck3.workingRadio := true
!truck3.mileage := 10

!new RentalAgreement('rentalAgreement3')
!rentalAgreement3.number := 5003
!rentalAgreement3.rentalDate := Date('2023-11-01')
!rentalAgreement3.anticipatedDuration := 2
!rentalAgreement3.depositPaid := 200.0
!rentalAgreement3.quotedDailyRate := 60.0
!rentalAgreement3.quotedRatePerMile := 0.45

!new Company('company2')
!company2.name := 'Construction Solutions'
!company2.address := '456 Industrial Way, AZ'
!company2.poorRisk := true
!company2.idNumber := 444555666

!insert (rentalOffice3, vehicle3) into RentalOfficeVehicle
!insert (rentalOffice3, truck3) into RentalOfficeVehicle

!insert (rentalOffice3, rentalAgreement3) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice1, rentalAgreement3) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement3, vehicle3) into RentalAgreementVehicle

!insert (rentalAgreement3, company2) into RentalAgreementCustomer
```
## Generation 2 summary
| General | Value | 
|---|---| 
| Syntax Errors | 1 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement3' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Industrial Way, AZ
```

# Generation 3
```
!new RentalOffice('rentalOffice4')
!rentalOffice4.name := 'City Central Rentals'
!rentalOffice4.number := 404
!rentalOffice4.address := '321 City Center Blvd, CT'

!new Vehicle('vehicle4')
!vehicle4.id := 1004
!vehicle4.registrationState := #CT
!vehicle4.licensePlateNumber := 'CT7890'
!vehicle4.vehicleTypeCode := #TRUCK24
!vehicle4.registrationLastMaintenanceDate := Date('2023-04-15')
!vehicle4.expirationDate := Date('2024-04-15')

!new Truck('truck4')
!truck4.id := 2004
!truck4.registrationState := #NY
!truck4.licensePlateNumber := 'NY4567'
!truck4.vehicleTypeCode := #TRUCK
!truck4.registrationLastMaintenanceDate := Date('2023-08-01')
!truck4.expirationDate := Date('2024-08-01')
!truck4.odometerReading := 25000
!truck4.gasTankCapacity := 60.0
!truck4.workingRadio := false
!truck4.mileage := 8

!new RentalAgreement('rentalAgreement4')
!rentalAgreement4.number := 5004
!rentalAgreement4.rentalDate := Date('2023-12-01')
!rentalAgreement4.anticipatedDuration := 7
!rentalAgreement4.depositPaid := 350.0
!rentalAgreement4.quotedDailyRate := 70.0
!rentalAgreement4.quotedRatePerMile := 0.35

!new Individual('individual3')
!individual3.name := 'Alice Johnson'
!individual3.address := '654 Hill Top Rd, AL'
!individual3.poorRisk := false
!individual3.homePhone := '205-555-0678'
!individual3.driverLicenseState := #AL
!individual3.driverLicenseNumber := 555666777
!individual3.driverLicenseExpirationDate := Date('2027-01-01')

!insert (rentalOffice4, vehicle4) into RentalOfficeVehicle
!insert (rentalOffice4, truck4) into RentalOfficeVehicle

!insert (rentalOffice4, rentalAgreement4) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice3, rentalAgreement4) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement4, truck4) into RentalAgreementVehicle

!insert (rentalAgreement4, individual3) into RentalAgreementCustomer
```
## Generation 3 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NY' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `NY'.
```
```
<input>:1:0: Variable `rentalOffice3' in expression `rentalOffice3' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement4' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
321 City Center Blvd, CT
```

# Generation 4
```
!new RentalOffice('rentalOffice5')
!rentalOffice5.name := 'Suburban Rentals'
!rentalOffice5.number := 505
!rentalOffice5.address := '989 Willow Dr, CT'

!new Vehicle('vehicle5')
!vehicle5.id := 1005
!vehicle5.registrationState := #DE
!vehicle5.licensePlateNumber := 'DE2345'
!vehicle5.vehicleTypeCode := #OPEN_TRAILER
!vehicle5.registrationLastMaintenanceDate := Date('2023-06-10')
!vehicle5.expirationDate := Date('2024-06-10')

!new Truck('truck5')
!truck5.id := 2005
!truck5.registrationState := #FL
!truck5.licensePlateNumber := 'FL6789'
!truck5.vehicleTypeCode := #TRUCK10
!truck5.registrationLastMaintenanceDate := Date('2023-09-12')
!truck5.expirationDate := Date('2024-09-12')
!truck5.odometerReading := 120000
!truck5.gasTankCapacity := 55.0
!truck5.workingRadio := true
!truck5.mileage := 5

!new RentalAgreement('rentalAgreement5')
!rentalAgreement5.number := 5005
!rentalAgreement5.rentalDate := Date('2024-01-15')
!rentalAgreement5.anticipatedDuration := 1
!rentalAgreement5.depositPaid := 50.0
!rentalAgreement5.quotedDailyRate := 49.0
!rentalAgreement5.quotedRatePerMile := 0.25

!new Company('company3')
!company3.name := 'Logistics Ltd'
!company3.address := '1122 Distribution Way, AL'
!company3.poorRisk := false
!company3.idNumber := 777888999

!insert (rentalOffice5, vehicle5) into RentalOfficeVehicle
!insert (rentalOffice5, truck5) into RentalOfficeVehicle

!insert (rentalOffice5, rentalAgreement5) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice1, rentalAgreement5) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement5, vehicle5) into RentalAgreementVehicle

!insert (rentalAgreement5, company3) into RentalAgreementCustomer
```
## Generation 4 summary
| General | Value | 
|---|---| 
| Syntax Errors | 1 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement5' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
1122 Distribution Way, AL
```

# Generation 5
```
!new RentalOffice('rentalOffice6')
!rentalOffice6.name := 'Airport Rentals'
!rentalOffice6.number := 606
!rentalOffice6.address := '303 Aviation Ln, AZ'

!new Vehicle('vehicle6')
!vehicle6.id := 1006
!vehicle6.registrationState := #NV
!vehicle6.licensePlateNumber := 'NV4321'
!vehicle6.vehicleTypeCode := #COVERED_TRAILER
!vehicle6.registrationLastMaintenanceDate := Date('2023-07-20')
!vehicle6.expirationDate := Date('2024-07-20')

!new Truck('truck6')
!truck6.id := 2006
!truck6.registrationState := #TX
!truck6.licensePlateNumber := 'TX9876'
!truck6.vehicleTypeCode := #TRUCK24
!truck6.registrationLastMaintenanceDate := Date('2023-10-15')
!truck6.expirationDate := Date('2024-10-15')
!truck6.odometerReading := 95000
!truck6.gasTankCapacity := 70.0
!truck6.workingRadio := false
!truck6.mileage := 9

!new RentalAgreement('rentalAgreement6')
!rentalAgreement6.number := 5006
!rentalAgreement6.rentalDate := Date('2024-02-01')
!rentalAgreement6.anticipatedDuration := 10
!rentalAgreement6.depositPaid := 300.0
!rentalAgreement6.quotedDailyRate := 100.0
!rentalAgreement6.quotedRatePerMile := 0.30

!new Individual('individual4')
!individual4.name := 'Robert Brown'
!individual4.address := '202 Birch St, NV'
!individual4.poorRisk := false
!individual4.homePhone := '702-555-3344'
!individual4.driverLicenseState := #NV
!individual4.driverLicenseNumber := 333444555
!individual4.driverLicenseExpirationDate := Date('2028-05-15')

!insert (rentalOffice6, vehicle6) into RentalOfficeVehicle
!insert (rentalOffice6, truck6) into RentalOfficeVehicle

!insert (rentalOffice6, rentalAgreement6) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice4, rentalAgreement6) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement6, truck6) into RentalAgreementVehicle

!insert (rentalAgreement6, individual4) into RentalAgreementCustomer
```
## Generation 5 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:31: Undefined enumeration literal `NV'.
```
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `TX'.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice4' in expression `rentalOffice4' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement6' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
303 Aviation Ln, AZ
```

# Generation 6
```
!new RentalOffice('rentalOffice7')
!rentalOffice7.name := 'Hillside Rentals'
!rentalOffice7.number := 707
!rentalOffice7.address := '789 Cliffside Rd, CO'

!new Vehicle('vehicle7')
!vehicle7.id := 1007
!vehicle7.registrationState := #CO
!vehicle7.licensePlateNumber := 'CO5678'
!vehicle7.vehicleTypeCode := #TRUCK10
!vehicle7.registrationLastMaintenanceDate := Date('2023-03-05')
!vehicle7.expirationDate := Date('2024-03-05')

!new Truck('truck7')
!truck7.id := 2007
!truck7.registrationState := #UT
!truck7.licensePlateNumber := 'UT9999'
!truck7.vehicleTypeCode := #TRUCK
!truck7.registrationLastMaintenanceDate := Date('2023-11-01')
!truck7.expirationDate := Date('2024-11-01')
!truck7.odometerReading := 45000
!truck7.gasTankCapacity := 50.0
!truck7.workingRadio := true
!truck7.mileage := 14

!new RentalAgreement('rentalAgreement7')
!rentalAgreement7.number := 5007
!rentalAgreement7.rentalDate := Date('2024-03-10')
!rentalAgreement7.anticipatedDuration := 4
!rentalAgreement7.depositPaid := 250.0
!rentalAgreement7.quotedDailyRate := 90.0
!rentalAgreement7.quotedRatePerMile := 0.28

!new Company('company4')
!company4.name := 'Transport Solutions'
!company4.address := '567 Corporate Dr, TX'
!company4.poorRisk := false
!company4.idNumber := 666777888

!insert (rentalOffice7, vehicle7) into RentalOfficeVehicle
!insert (rentalOffice7, truck7) into RentalOfficeVehicle

!insert (rentalOffice7, rentalAgreement7) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice2, rentalAgreement7) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement7, vehicle7) into RentalAgreementVehicle

!insert (rentalAgreement7, company4) into RentalAgreementCustomer
```
## Generation 6 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `UT'.
```
```
<input>:1:0: Variable `rentalOffice2' in expression `rentalOffice2' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement7' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
789 Cliffside Rd, CO
```

# Generation 7
```
!new RentalOffice('rentalOffice8')
!rentalOffice8.name := 'Urban Mobility Rentals'
!rentalOffice8.number := 808
!rentalOffice8.address := '400 Downtown Cir, AZ'

!new Vehicle('vehicle8')
!vehicle8.id := 1008
!vehicle8.registrationState := #AZ
!vehicle8.licensePlateNumber := 'AZ2233'
!vehicle8.vehicleTypeCode := #COVERED_TRAILER
!vehicle8.registrationLastMaintenanceDate := Date('2023-08-15')
!vehicle8.expirationDate := Date('2024-08-15')

!new Truck('truck8')
!truck8.id := 2008
!truck8.registrationState := #NV
!truck8.licensePlateNumber := 'NV5566'
!truck8.vehicleTypeCode := #TRUCK10
!truck8.registrationLastMaintenanceDate := Date('2023-12-01')
!truck8.expirationDate := Date('2024-12-01')
!truck8.odometerReading := 70000
!truck8.gasTankCapacity := 52.0
!truck8.workingRadio := false
!truck8.mileage := 13

!new RentalAgreement('rentalAgreement8')
!rentalAgreement8.number := 5008
!rentalAgreement8.rentalDate := Date('2024-04-15')
!rentalAgreement8.anticipatedDuration := 12
!rentalAgreement8.depositPaid := 400.0
!rentalAgreement8.quotedDailyRate := 80.0
!rentalAgreement8.quotedRatePerMile := 0.32

!new Individual('individual5')
!individual5.name := 'Emily Clark'
!individual5.address := '100 Lakeside Ave, CT'
!individual5.poorRisk := true
!individual5.homePhone := '860-555-9988'
!individual5.driverLicenseState := #CT
!individual5.driverLicenseNumber := 222333444
!individual5.driverLicenseExpirationDate := Date('2026-12-10')

!insert (rentalOffice8, vehicle8) into RentalOfficeVehicle
!insert (rentalOffice8, truck8) into RentalOfficeVehicle

!insert (rentalOffice8, rentalAgreement8) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice6, rentalAgreement8) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement8, truck8) into RentalAgreementVehicle

!insert (rentalAgreement8, individual5) into RentalAgreementCustomer
```
## Generation 7 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice6' in expression `rentalOffice6' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement8' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
400 Downtown Cir, AZ
```

# Generation 8
```
!new RentalOffice('rentalOffice9')
!rentalOffice9.name := 'Lakeside Rentals'
!rentalOffice9.number := 909
!rentalOffice9.address := '120 Lake St, FL'

!new Vehicle('vehicle9')
!vehicle9.id := 1009
!vehicle9.registrationState := #FL
!vehicle9.licensePlateNumber := 'FL3344'
!vehicle9.vehicleTypeCode := #OPEN_TRAILER
!vehicle9.registrationLastMaintenanceDate := Date('2023-09-20')
!vehicle9.expirationDate := Date('2024-09-20')

!new Truck('truck9')
!truck9.id := 2009
!truck9.registrationState := #TX
!truck9.licensePlateNumber := 'TX7788'
!truck9.vehicleTypeCode := #TRUCK24
!truck9.registrationLastMaintenanceDate := Date('2023-11-11')
!truck9.expirationDate := Date('2024-11-11')
!truck9.odometerReading := 30000
!truck9.gasTankCapacity := 65.0
!truck9.workingRadio := true
!truck9.mileage := 11

!new RentalAgreement('rentalAgreement9')
!rentalAgreement9.number := 5009
!rentalAgreement9.rentalDate := Date('2024-05-20')
!rentalAgreement9.anticipatedDuration := 6
!rentalAgreement9.depositPaid := 275.0
!rentalAgreement9.quotedDailyRate := 95.0
!rentalAgreement9.quotedRatePerMile := 0.38

!new Company('company5')
!company5.name := 'Green Earth Logistics'
!company5.address := '200 Eco Blvd, CA'
!company5.poorRisk := true
!company5.idNumber := 555666777

!insert (rentalOffice9, vehicle9) into RentalOfficeVehicle
!insert (rentalOffice9, truck9) into RentalOfficeVehicle

!insert (rentalOffice9, rentalAgreement9) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice5, rentalAgreement9) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement9, vehicle9) into RentalAgreementVehicle

!insert (rentalAgreement9, company5) into RentalAgreementCustomer
```
## Generation 8 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `TX'.
```
```
<input>:1:0: Variable `rentalOffice5' in expression `rentalOffice5' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement9' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
200 Eco Blvd, CA
```

# Generation 9
```
!new RentalOffice('rentalOffice10')
!rentalOffice10.name := 'Metro Rentals'
!rentalOffice10.number := 1010
!rentalOffice10.address := '800 Riverside Ave, CA'

!new Vehicle('vehicle10')
!vehicle10.id := 1010
!vehicle10.registrationState := #AL
!vehicle10.licensePlateNumber := 'AL4567'
!vehicle10.vehicleTypeCode := #TRUCK
!vehicle10.registrationLastMaintenanceDate := Date('2023-05-10')
!vehicle10.expirationDate := Date('2024-05-10')

!new Truck('truck10')
!truck10.id := 2010
!truck10.registrationState := #CT
!truck10.licensePlateNumber := 'CT9988'
!truck10.vehicleTypeCode := #TRUCK
!truck10.registrationLastMaintenanceDate := Date('2023-10-20')
!truck10.expirationDate := Date('2024-10-20')
!truck10.odometerReading := 60000
!truck10.gasTankCapacity := 58.0
!truck10.workingRadio := false
!truck10.mileage := 7

!new RentalAgreement('rentalAgreement10')
!rentalAgreement10.number := 5010
!rentalAgreement10.rentalDate := Date('2024-06-15')
!rentalAgreement10.anticipatedDuration := 8
!rentalAgreement10.depositPaid := 320.0
!rentalAgreement10.quotedDailyRate := 85.0
!rentalAgreement10.quotedRatePerMile := 0.42

!new Individual('individual6')
!individual6.name := 'David Wilson'
!individual6.address := '123 Maple Ln, AZ'
!individual6.poorRisk := false
!individual6.homePhone := '602-555-1122'
!individual6.driverLicenseState := #AZ
!individual6.driverLicenseNumber := 111008888
!individual6.driverLicenseExpirationDate := Date('2027-09-30')

!insert (rentalOffice10, vehicle10) into RentalOfficeVehicle
!insert (rentalOffice10, truck10) into RentalOfficeVehicle

!insert (rentalOffice10, rentalAgreement10) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice7, rentalAgreement10) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement10, truck10) into RentalAgreementVehicle

!insert (rentalAgreement10, individual6) into RentalAgreementCustomer
```
## Generation 9 summary
| General | Value | 
|---|---| 
| Syntax Errors | 1 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: Variable `rentalOffice7' in expression `rentalOffice7' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement10' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
123 Maple Ln, AZ
```

# Generation 10
```
!new RentalOffice('rentalOffice11')
!rentalOffice11.name := 'Transport Hub Rentals'
!rentalOffice11.number := 1111
!rentalOffice11.address := '1500 Industry Pkwy, AL'

!new Vehicle('vehicle11')
!vehicle11.id := 1011
!vehicle11.registrationState := #GA
!vehicle11.licensePlateNumber := 'GA7894'
!vehicle11.vehicleTypeCode := #TRUCK24
!vehicle11.registrationLastMaintenanceDate := Date('2023-02-15')
!vehicle11.expirationDate := Date('2024-02-15')

!new Truck('truck11')
!truck11.id := 2011
!truck11.registrationState := #TN
!truck11.licensePlateNumber := 'TN1552'
!truck11.vehicleTypeCode := #TRUCK10
!truck11.registrationLastMaintenanceDate := Date('2023-09-05')
!truck11.expirationDate := Date('2024-09-05')
!truck11.odometerReading := 82000
!truck11.gasTankCapacity := 75.0
!truck11.workingRadio := true
!truck11.mileage := 16

!new RentalAgreement('rentalAgreement11')
!rentalAgreement11.number := 5011
!rentalAgreement11.rentalDate := Date('2024-07-25')
!rentalAgreement11.anticipatedDuration := 14
!rentalAgreement11.depositPaid := 500.0
!rentalAgreement11.quotedDailyRate := 95.0
!rentalAgreement11.quotedRatePerMile := 0.40

!new Company('company6')
!company6.name := 'Big Transport Co.'
!company6.address := '456 Logistics Ave, TX'
!company6.poorRisk := false
!company6.idNumber := 88889999

!insert (rentalOffice11, vehicle11) into RentalOfficeVehicle
!insert (rentalOffice11, truck11) into RentalOfficeVehicle

!insert (rentalOffice11, rentalAgreement11) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice3, rentalAgreement11) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement11, vehicle11) into RentalAgreementVehicle

!insert (rentalAgreement11, company6) into RentalAgreementCustomer
```
## Generation 10 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#TN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `TN'.
```
```
<input>:1:0: Variable `rentalOffice3' in expression `rentalOffice3' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement11' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
1500 Industry Pkwy, AL
```
```
456 Logistics Ave, TX
```

# Generation 11
```
!new RentalOffice('rentalOffice12')
!rentalOffice12.name := 'Capital Rentals'
!rentalOffice12.number := 1212
!rentalOffice12.address := '900 Constitution Ave, DC'

!new Vehicle('vehicle12')
!vehicle12.id := 1012
!vehicle12.registrationState := #DC
!vehicle12.licensePlateNumber := 'DC5678'
!vehicle12.vehicleTypeCode := #OPEN_TRAILER
!vehicle12.registrationLastMaintenanceDate := Date('2023-04-20')
!vehicle12.expirationDate := Date('2024-04-20')

!new Truck('truck12')
!truck12.id := 2012
!truck12.registrationState := #NC
!truck12.licensePlateNumber := 'NC3344'
!truck12.vehicleTypeCode := #TRUCK
!truck12.registrationLastMaintenanceDate := Date('2023-11-22')
!truck12.expirationDate := Date('2024-11-22')
!truck12.odometerReading := 15000
!truck12.gasTankCapacity := 68.0
!truck12.workingRadio := false
!truck12.mileage := 12

!new RentalAgreement('rentalAgreement12')
!rentalAgreement12.number := 5012
!rentalAgreement12.rentalDate := Date('2024-08-05')
!rentalAgreement12.anticipatedDuration := 20
!rentalAgreement12.depositPaid := 700.0
!rentalAgreement12.quotedDailyRate := 120.0
!rentalAgreement12.quotedRatePerMile := 0.45

!new Individual('individual7')
!individual7.name := 'Samantha Lee'
!individual7.address := '301 River Rd, WV'
!individual7.poorRisk := true
!individual7.homePhone := '304-555-7766'
!individual7.driverLicenseState := #WV
!individual7.driverLicenseNumber := 444555666
!individual7.driverLicenseExpirationDate := Date('2026-03-15')

!insert (rentalOffice12, vehicle12) into RentalOfficeVehicle
!insert (rentalOffice12, truck12) into RentalOfficeVehicle

!insert (rentalOffice12, rentalAgreement12) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice9, rentalAgreement12) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement12, truck12) into RentalAgreementVehicle

!insert (rentalAgreement12, individual7) into RentalAgreementCustomer
```
## Generation 11 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#DC' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `DC'.
```
```
<input>:1:0: generation of expression `#NC' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NC'.
```
```
<input>:1:0: generation of expression `#WV' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `WV'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement12' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
900 Constitution Ave, DC
```

# Generation 12
```
!new RentalOffice('rentalOffice13')
!rentalOffice13.name := 'Seaside Rentals'
!rentalOffice13.number := 1313
!rentalOffice13.address := '1600 Oceanview Blvd, FL'

!new Vehicle('vehicle13')
!vehicle13.id := 1013
!vehicle13.registrationState := #VA
!vehicle13.licensePlateNumber := 'VA8910'
!vehicle13.vehicleTypeCode := #COVERED_TRAILER
!vehicle13.registrationLastMaintenanceDate := Date('2023-06-10')
!vehicle13.expirationDate := Date('2024-06-10')

!new Truck('truck13')
!truck13.id := 2013
!truck13.registrationState := #GA
!truck13.licensePlateNumber := 'GA4455'
!truck13.vehicleTypeCode := #TRUCK24
!truck13.registrationLastMaintenanceDate := Date('2023-12-05')
!truck13.expirationDate := Date('2024-12-05')
!truck13.odometerReading := 92000
!truck13.gasTankCapacity := 62.0
!truck13.workingRadio := true
!truck13.mileage := 10

!new RentalAgreement('rentalAgreement13')
!rentalAgreement13.number := 5013
!rentalAgreement13.rentalDate := Date('2024-09-10')
!rentalAgreement13.anticipatedDuration := 3
!rentalAgreement13.depositPaid := 180.0
!rentalAgreement13.quotedDailyRate := 70.0
!rentalAgreement13.quotedRatePerMile := 0.33

!new Company('company7')
!company7.name := 'Atlantic Freight'
!company7.address := '880 Harbor Lane, NY'
!company7.poorRisk := false
!company7.idNumber := 123123123

!insert (rentalOffice13, vehicle13) into RentalOfficeVehicle
!insert (rentalOffice13, truck13) into RentalOfficeVehicle

!insert (rentalOffice13, rentalAgreement13) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice10, rentalAgreement13) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement13, vehicle13) into RentalAgreementVehicle

!insert (rentalAgreement13, company7) into RentalAgreementCustomer
```
## Generation 12 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#VA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `VA'.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `GA'.
```
```
<input>:1:0: Variable `rentalOffice10' in expression `rentalOffice10' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement13' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
1600 Oceanview Blvd, FL
```
```
880 Harbor Lane, NY
```

# Generation 13
```
!new RentalOffice('rentalOffice14')
!rentalOffice14.name := 'Urban Drive Rentals'
!rentalOffice14.number := 1414
!rentalOffice14.address := '222 Central Park Ave, NY'

!new Vehicle('vehicle14')
!vehicle14.id := 1014
!vehicle14.registrationState := #NY
!vehicle14.licensePlateNumber := 'NY1235'
!vehicle14.vehicleTypeCode := #TRUCK10
!vehicle14.registrationLastMaintenanceDate := Date('2023-07-25')
!vehicle14.expirationDate := Date('2024-07-25')

!new Truck('truck14')
!truck14.id := 2014
!truck14.registrationState := #MA
!truck14.licensePlateNumber := 'MA6677'
!truck14.vehicleTypeCode := #TRUCK24
!truck14.registrationLastMaintenanceDate := Date('2023-10-30')
!truck14.expirationDate := Date('2024-10-30')
!truck14.odometerReading := 55000
!truck14.gasTankCapacity := 48.0
!truck14.workingRadio := false
!truck14.mileage := 11

!new RentalAgreement('rentalAgreement14')
!rentalAgreement14.number := 5014
!rentalAgreement14.rentalDate := Date('2024-10-01')
!rentalAgreement14.anticipatedDuration := 5
!rentalAgreement14.depositPaid := 250.0
!rentalAgreement14.quotedDailyRate := 85.0
!rentalAgreement14.quotedRatePerMile := 0.29

!new Individual('individual8')
!individual8.name := 'Chris Evans'
!individual8.address := '456 Liberty Ave, DE'
!individual8.poorRisk := false
!individual8.homePhone := '302-555-4455'
!individual8.driverLicenseState := #DE
!individual8.driverLicenseNumber := 889977665
!individual8.driverLicenseExpirationDate := Date('2028-02-22')

!insert (rentalOffice14, vehicle14) into RentalOfficeVehicle
!insert (rentalOffice14, truck14) into RentalOfficeVehicle

!insert (rentalOffice14, rentalAgreement14) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice1, rentalAgreement14) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement14, truck14) into RentalAgreementVehicle

!insert (rentalAgreement14, individual8) into RentalAgreementCustomer
```
## Generation 13 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NY' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NY'.
```
```
<input>:1:0: generation of expression `#MA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `MA'.
```
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement14' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
222 Central Park Ave, NY
```

# Generation 14
```
!new RentalOffice('rentalOffice15')
!rentalOffice15.name := 'Express Rentals'
!rentalOffice15.number := 1515
!rentalOffice15.address := '555 Expressway St, CA'

!new Vehicle('vehicle15')
!vehicle15.id := 1015
!vehicle15.registrationState := #OR
!vehicle15.licensePlateNumber := 'OR6789'
!vehicle15.vehicleTypeCode := #TRUCK
!vehicle15.registrationLastMaintenanceDate := Date('2023-03-15')
!vehicle15.expirationDate := Date('2024-03-15')

!new Truck('truck15')
!truck15.id := 2015
!truck15.registrationState := #WA
!truck15.licensePlateNumber := 'WA1122'
!truck15.vehicleTypeCode := #TRUCK24
!truck15.registrationLastMaintenanceDate := Date('2023-12-20')
!truck15.expirationDate := Date('2024-12-20')
!truck15.odometerReading := 80000
!truck15.gasTankCapacity := 54.0
!truck15.workingRadio := true
!truck15.mileage := 9

!new RentalAgreement('rentalAgreement15')
!rentalAgreement15.number := 5015
!rentalAgreement15.rentalDate := Date('2024-11-15')
!rentalAgreement15.anticipatedDuration := 2
!rentalAgreement15.depositPaid := 175.0
!rentalAgreement15.quotedDailyRate := 60.0
!rentalAgreement15.quotedRatePerMile := 0.25

!new Company('company8')
!company8.name := 'Quick Transport'
!company8.address := '123 Rapid Rd, NV'
!company8.poorRisk := false
!company8.idNumber := 55667788

!insert (rentalOffice15, vehicle15) into RentalOfficeVehicle
!insert (rentalOffice15, truck15) into RentalOfficeVehicle

!insert (rentalOffice15, rentalAgreement15) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice8, rentalAgreement15) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement15, vehicle15) into RentalAgreementVehicle

!insert (rentalAgreement15, company8) into RentalAgreementCustomer
```
## Generation 14 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `OR'.
```
```
<input>:1:0: generation of expression `#WA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WA'.
```
```
<input>:1:0: Variable `rentalOffice8' in expression `rentalOffice8' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement15' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
555 Expressway St, CA
```
```
123 Rapid Rd, NV
```

# Generation 15
```
!new RentalOffice('rentalOffice16')
!rentalOffice16.name := 'Global Rentals'
!rentalOffice16.number := 1616
!rentalOffice16.address := '300 International Blvd, CA'

!new Vehicle('vehicle16')
!vehicle16.id := 1016
!vehicle16.registrationState := #TX
!vehicle16.licensePlateNumber := 'TX3344'
!vehicle16.vehicleTypeCode := #COVERED_TRAILER
!vehicle16.registrationLastMaintenanceDate := Date('2023-05-30')
!vehicle16.expirationDate := Date('2024-05-30')

!new Truck('truck16')
!truck16.id := 2016
!truck16.registrationState := #FL
!truck16.licensePlateNumber := 'FL8899'
!truck16.vehicleTypeCode := #TRUCK10
!truck16.registrationLastMaintenanceDate := Date('2023-10-18')
!truck16.expirationDate := Date('2024-10-18')
!truck16.odometerReading := 90000
!truck16.gasTankCapacity := 40.0
!truck16.workingRadio := false
!truck16.mileage := 19

!new RentalAgreement('rentalAgreement16')
!rentalAgreement16.number := 5016
!rentalAgreement16.rentalDate := Date('2025-01-01')
!rentalAgreement16.anticipatedDuration := 7
!rentalAgreement16.depositPaid := 450.0
!rentalAgreement16.quotedDailyRate := 75.0
!rentalAgreement16.quotedRatePerMile := 0.40

!new Individual('individual9')
!individual9.name := 'Natalie Green'
!individual9.address := '789 Forest Dr, GA'
!individual9.poorRisk := true
!individual9.homePhone := '912-555-0987'
!individual9.driverLicenseState := #GA
!individual9.driverLicenseNumber := 101010101
!individual9.driverLicenseExpirationDate := Date('2027-06-30')

!insert (rentalOffice16, vehicle16) into RentalOfficeVehicle
!insert (rentalOffice16, truck16) into RentalOfficeVehicle

!insert (rentalOffice16, rentalAgreement16) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice12, rentalAgreement16) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement16, truck16) into RentalAgreementVehicle

!insert (rentalAgreement16, individual9) into RentalAgreementCustomer
```
## Generation 15 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `TX'.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `GA'.
```
```
<input>:1:0: Variable `rentalOffice12' in expression `rentalOffice12' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement16' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 2 | 2 | 100.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

# Generation 16
```
!new RentalOffice('rentalOffice17')
!rentalOffice17.name := 'Downtown Transit Rentals'
!rentalOffice17.number := 1717
!rentalOffice17.address := '456 Broadway, NY'

!new Vehicle('vehicle17')
!vehicle17.id := 1017
!vehicle17.registrationState := #NJ
!vehicle17.licensePlateNumber := 'NJ3345'
!vehicle17.vehicleTypeCode := #OPEN_TRAILER
!vehicle17.registrationLastMaintenanceDate := Date('2023-09-15')
!vehicle17.expirationDate := Date('2024-09-15')

!new Truck('truck17')
!truck17.id := 2017
!truck17.registrationState := #PA
!truck17.licensePlateNumber := 'PA5566'
!truck17.vehicleTypeCode := #TRUCK24
!truck17.registrationLastMaintenanceDate := Date('2023-11-25')
!truck17.expirationDate := Date('2024-11-25')
!truck17.odometerReading := 45000
!truck17.gasTankCapacity := 46.0
!truck17.workingRadio := true
!truck17.mileage := 13

!new RentalAgreement('rentalAgreement17')
!rentalAgreement17.number := 5017
!rentalAgreement17.rentalDate := Date('2024-12-15')
!rentalAgreement17.anticipatedDuration := 15
!rentalAgreement17.depositPaid := 600.0
!rentalAgreement17.quotedDailyRate := 90.0
!rentalAgreement17.quotedRatePerMile := 0.35

!new Company('company9')
!company9.name := 'East Coast Movers'
!company9.address := '625 Ocean Dr, NJ'
!company9.poorRisk := false
!company9.idNumber := 999111888

!insert (rentalOffice17, vehicle17) into RentalOfficeVehicle
!insert (rentalOffice17, truck17) into RentalOfficeVehicle

!insert (rentalOffice17, rentalAgreement17) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice14, rentalAgreement17) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement17, truck17) into RentalAgreementVehicle

!insert (rentalAgreement17, company9) into RentalAgreementCustomer
```
## Generation 16 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NJ' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NJ'.
```
```
<input>:1:0: generation of expression `#PA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `PA'.
```
```
<input>:1:0: Variable `rentalOffice14' in expression `rentalOffice14' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement17' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Broadway, NY
```

# Generation 17
```
!new RentalOffice('rentalOffice18')
!rentalOffice18.name := 'Highway Rentals'
!rentalOffice18.number := 1818
!rentalOffice18.address := '777 Freeway Rd, TX'

!new Vehicle('vehicle18')
!vehicle18.id := 1018
!vehicle18.registrationState := #NM
!vehicle18.licensePlateNumber := 'NM4321'
!vehicle18.vehicleTypeCode := #TRUCK24
!vehicle18.registrationLastMaintenanceDate := Date('2023-08-20')
!vehicle18.expirationDate := Date('2024-08-20')

!new Truck('truck18')
!truck18.id := 2018
!truck18.registrationState := #LA
!truck18.licensePlateNumber := 'LA6587'
!truck18.vehicleTypeCode := #TRUCK10
!truck18.registrationLastMaintenanceDate := Date('2023-11-10')
!truck18.expirationDate := Date('2024-11-10')
!truck18.odometerReading := 70000
!truck18.gasTankCapacity := 65.0
!truck18.workingRadio := false
!truck18.mileage := 12

!new RentalAgreement('rentalAgreement18')
!rentalAgreement18.number := 5018
!rentalAgreement18.rentalDate := Date('2025-02-12')
!rentalAgreement18.anticipatedDuration := 4
!rentalAgreement18.depositPaid := 300.0
!rentalAgreement18.quotedDailyRate := 85.0
!rentalAgreement18.quotedRatePerMile := 0.36

!new Individual('individual10')
!individual10.name := 'Oliver Smith'
!individual10.address := '800 Timber St, AL'
!individual10.poorRisk := false
!individual10.homePhone := '205-555-3312'
!individual10.driverLicenseState := #AL
!individual10.driverLicenseNumber := 876543210
!individual10.driverLicenseExpirationDate := Date('2029-12-01')

!insert (rentalOffice18, vehicle18) into RentalOfficeVehicle
!insert (rentalOffice18, truck18) into RentalOfficeVehicle

!insert (rentalOffice18, rentalAgreement18) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice5, rentalAgreement18) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement18, vehicle18) into RentalAgreementVehicle

!insert (rentalAgreement18, individual10) into RentalAgreementCustomer
```
## Generation 17 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NM'.
```
```
<input>:1:0: generation of expression `#LA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `LA'.
```
```
<input>:1:0: Variable `rentalOffice5' in expression `rentalOffice5' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement18' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
800 Timber St, AL
```

# Generation 18
```
!new RentalOffice('rentalOffice19')
!rentalOffice19.name := 'Summit Rentals'
!rentalOffice19.number := 1919
!rentalOffice19.address := '123 Mountain Rd, CO'

!new Vehicle('vehicle19')
!vehicle19.id := 1019
!vehicle19.registrationState := #UT
!vehicle19.licensePlateNumber := 'UT5678'
!vehicle19.vehicleTypeCode := #TRUCK24
!vehicle19.registrationLastMaintenanceDate := Date('2023-11-01')
!vehicle19.expirationDate := Date('2024-11-01')

!new Truck('truck19')
!truck19.id := 2019
!truck19.registrationState := #WY
!truck19.licensePlateNumber := 'WY1234'
!truck19.vehicleTypeCode := #TRUCK
!truck19.registrationLastMaintenanceDate := Date('2023-12-01')
!truck19.expirationDate := Date('2024-12-01')
!truck19.odometerReading := 150000
!truck19.gasTankCapacity := 70.0
!truck19.workingRadio := true
!truck19.mileage := 5

!new RentalAgreement('rentalAgreement19')
!rentalAgreement19.number := 5019
!rentalAgreement19.rentalDate := Date('2025-03-15')
!rentalAgreement19.anticipatedDuration := 9
!rentalAgreement19.depositPaid := 450.0
!rentalAgreement19.quotedDailyRate := 95.0
!rentalAgreement19.quotedRatePerMile := 0.50

!new Company('company10')
!company10.name := 'Mountain Transport Co.'
!company10.address := '456 Summit Blvd, NV'
!company10.poorRisk := true
!company10.idNumber := 101010101

!insert (rentalOffice19, vehicle19) into RentalOfficeVehicle
!insert (rentalOffice19, truck19) into RentalOfficeVehicle

!insert (rentalOffice19, rentalAgreement19) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice7, rentalAgreement19) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement19, truck19) into RentalAgreementVehicle

!insert (rentalAgreement19, company10) into RentalAgreementCustomer
```
## Generation 18 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `UT'.
```
```
<input>:1:0: generation of expression `#WY' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WY'.
```
```
<input>:1:0: Variable `rentalOffice7' in expression `rentalOffice7' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement19' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Summit Blvd, NV
```

# Generation 19
```
!new RentalOffice('rentalOffice20')
!rentalOffice20.name := 'Desert Rentals'
!rentalOffice20.number := 2020
!rentalOffice20.address := '500 Desert Way, AZ'

!new Vehicle('vehicle20')
!vehicle20.id := 1020
!vehicle20.registrationState := #NV
!vehicle20.licensePlateNumber := 'NV8765'
!vehicle20.vehicleTypeCode := #COVERED_TRAILER
!vehicle20.registrationLastMaintenanceDate := Date('2023-03-22')
!vehicle20.expirationDate := Date('2024-03-22')

!new Truck('truck20')
!truck20.id := 2020
!truck20.registrationState := #AZ
!truck20.licensePlateNumber := 'AZ5432'
!truck20.vehicleTypeCode := #TRUCK10
!truck20.registrationLastMaintenanceDate := Date('2023-07-14')
!truck20.expirationDate := Date('2024-07-14')
!truck20.odometerReading := 130000
!truck20.gasTankCapacity := 55.0
!truck20.workingRadio := false
!truck20.mileage := 8

!new RentalAgreement('rentalAgreement20')
!rentalAgreement20.number := 5020
!rentalAgreement20.rentalDate := Date('2025-04-25')
!rentalAgreement20.anticipatedDuration := 6
!rentalAgreement20.depositPaid := 300.0
!rentalAgreement20.quotedDailyRate := 70.0
!rentalAgreement20.quotedRatePerMile := 0.47

!new Individual('individual11')
!individual11.name := 'Sophia Turner'
!individual11.address := '333 Sun Blvd, NM'
!individual11.poorRisk := true
!individual11.homePhone := '505-555-9898'
!individual11.driverLicenseState := #NM
!individual11.driverLicenseNumber := 909090909
!individual11.driverLicenseExpirationDate := Date('2028-09-09')

!insert (rentalOffice20, vehicle20) into RentalOfficeVehicle
!insert (rentalOffice20, truck20) into RentalOfficeVehicle

!insert (rentalOffice20, rentalAgreement20) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice18, rentalAgreement20) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement20, truck20) into RentalAgreementVehicle

!insert (rentalAgreement20, individual11) into RentalAgreementCustomer
```
## Generation 19 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NV'.
```
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `NM'.
```
```
<input>:1:0: Variable `rentalOffice18' in expression `rentalOffice18' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement20' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
500 Desert Way, AZ
```
```
333 Sun Blvd, NM
```

# Generation 20
```
!new RentalOffice('rentalOffice21')
!rentalOffice21.name := 'Coastal Rentals'
!rentalOffice21.number := 2121
!rentalOffice21.address := '100 Shoreline Dr, CA'

!new Vehicle('vehicle21')
!vehicle21.id := 1021
!vehicle21.registrationState := #CA
!vehicle21.licensePlateNumber := 'CA7654'
!vehicle21.vehicleTypeCode := #OPEN_TRAILER
!vehicle21.registrationLastMaintenanceDate := Date('2023-10-01')
!vehicle21.expirationDate := Date('2024-10-01')

!new Truck('truck21')
!truck21.id := 2021
!truck21.registrationState := #OR
!truck21.licensePlateNumber := 'OR6789'
!truck21.vehicleTypeCode := #TRUCK
!truck21.registrationLastMaintenanceDate := Date('2024-01-15')
!truck21.expirationDate := Date('2025-01-15')
!truck21.odometerReading := 9000
!truck21.gasTankCapacity := 65.0
!truck21.workingRadio := true
!truck21.mileage := 16

!new RentalAgreement('rentalAgreement21')
!rentalAgreement21.number := 5021
!rentalAgreement21.rentalDate := Date('2025-06-01')
!rentalAgreement21.anticipatedDuration := 12
!rentalAgreement21.depositPaid := 600.0
!rentalAgreement21.quotedDailyRate := 105.0
!rentalAgreement21.quotedRatePerMile := 0.55

!new Company('company11')
!company11.name := 'Seaside Haulers'
!company11.address := '456 Wave Ave, WA'
!company11.poorRisk := false
!company11.idNumber := 212121212

!insert (rentalOffice21, vehicle21) into RentalOfficeVehicle
!insert (rentalOffice21, truck21) into RentalOfficeVehicle

!insert (rentalOffice21, rentalAgreement21) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice16, rentalAgreement21) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement21, vehicle21) into RentalAgreementVehicle

!insert (rentalAgreement21, company11) into RentalAgreementCustomer
```
## Generation 20 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `OR'.
```
```
<input>:1:0: Variable `rentalOffice16' in expression `rentalOffice16' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement21' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Wave Ave, WA
```

# Generation 21
```
!new RentalOffice('rentalOffice22')
!rentalOffice22.name := 'City Edge Rentals'
!rentalOffice22.number := 2222
!rentalOffice22.address := '123 Edge Pkwy, IL'

!new Vehicle('vehicle22')
!vehicle22.id := 1022
!vehicle22.registrationState := #IL
!vehicle22.licensePlateNumber := 'IL4567'
!vehicle22.vehicleTypeCode := #TRUCK10
!vehicle22.registrationLastMaintenanceDate := Date('2023-05-05')
!vehicle22.expirationDate := Date('2024-05-05')

!new Truck('truck22')
!truck22.id := 2022
!truck22.registrationState := #IN
!truck22.licensePlateNumber := 'IN1122'
!truck22.vehicleTypeCode := #TRUCK24
!truck22.registrationLastMaintenanceDate := Date('2024-03-10')
!truck22.expirationDate := Date('2025-03-10')
!truck22.odometerReading := 30000
!truck22.gasTankCapacity := 50.0
!truck22.workingRadio := false
!truck22.mileage := 10

!new RentalAgreement('rentalAgreement22')
!rentalAgreement22.number := 5022
!rentalAgreement22.rentalDate := Date('2025-07-20')
!rentalAgreement22.anticipatedDuration := 8
!rentalAgreement22.depositPaid := 550.0
!rentalAgreement22.quotedDailyRate := 88.0
!rentalAgreement22.quotedRatePerMile := 0.30

!new Individual('individual12')
!individual12.name := 'Daniel White'
!individual12.address := '101 Lakeview Dr, IN'
!individual12.poorRisk := true
!individual12.homePhone := '317-555-6600'
!individual12.driverLicenseState := #IN
!individual12.driverLicenseNumber := 1010101010
!individual12.driverLicenseExpirationDate := Date('2029-07-17')

!insert (rentalOffice22, vehicle22) into RentalOfficeVehicle
!insert (rentalOffice22, truck22) into RentalOfficeVehicle

!insert (rentalOffice22, rentalAgreement22) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice13, rentalAgreement22) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement22, truck22) into RentalAgreementVehicle

!insert (rentalAgreement22, individual12) into RentalAgreementCustomer
```
## Generation 21 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#IL' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `IL'.
```
```
<input>:1:0: generation of expression `#IN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `IN'.
```
```
<input>:1:0: generation of expression `#IN' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `IN'.
```
```
<input>:1:0: Variable `rentalOffice13' in expression `rentalOffice13' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement22' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
123 Edge Pkwy, IL
```
```
101 Lakeview Dr, IN
```

# Generation 22
```
!new RentalOffice('rentalOffice23')
!rentalOffice23.name := 'Valley Rentals'
!rentalOffice23.number := 2323
!rentalOffice23.address := '789 Valley Rd, CO'

!new Vehicle('vehicle23')
!vehicle23.id := 1023
!vehicle23.registrationState := #NM
!vehicle23.licensePlateNumber := 'NM3456'
!vehicle23.vehicleTypeCode := #OPEN_TRAILER
!vehicle23.registrationLastMaintenanceDate := Date('2023-07-07')
!vehicle23.expirationDate := Date('2024-07-07')

!new Truck('truck23')
!truck23.id := 2023
!truck23.registrationState := #NV
!truck23.licensePlateNumber := 'NV8765'
!truck23.vehicleTypeCode := #TRUCK10
!truck23.registrationLastMaintenanceDate := Date('2024-02-20')
!truck23.expirationDate := Date('2025-02-20')
!truck23.odometerReading := 75000
!truck23.gasTankCapacity := 55.0
!truck23.workingRadio := true
!truck23.mileage := 18

!new RentalAgreement('rentalAgreement23')
!rentalAgreement23.number := 5023
!rentalAgreement23.rentalDate := Date('2025-09-01')
!rentalAgreement23.anticipatedDuration := 10
!rentalAgreement23.depositPaid := 675.0
!rentalAgreement23.quotedDailyRate := 92.0
!rentalAgreement23.quotedRatePerMile := 0.45

!new Company('company12')
!company12.name := 'Desert Freight Co.'
!company12.address := '555 Sand Dunes Ave, AZ'
!company12.poorRisk := false
!company12.idNumber := 1212121212

!insert (rentalOffice23, vehicle23) into RentalOfficeVehicle
!insert (rentalOffice23, truck23) into RentalOfficeVehicle

!insert (rentalOffice23, rentalAgreement23) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice19, rentalAgreement23) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement23, truck23) into RentalAgreementVehicle

!insert (rentalAgreement23, company12) into RentalAgreementCustomer
```
## Generation 22 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NM'.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice19' in expression `rentalOffice19' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement23' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
555 Sand Dunes Ave, AZ
```

# Generation 23
```
!new RentalOffice('rentalOffice24')
!rentalOffice24.name := 'Pinewood Rentals'
!rentalOffice24.number := 2424
!rentalOffice24.address := '400 Pine St, ME'

!new Vehicle('vehicle24')
!vehicle24.id := 1024
!vehicle24.registrationState := #ME
!vehicle24.licensePlateNumber := 'ME2345'
!vehicle24.vehicleTypeCode := #TRUCK
!vehicle24.registrationLastMaintenanceDate := Date('2023-08-12')
!vehicle24.expirationDate := Date('2024-08-12')

!new Truck('truck24')
!truck24.id := 2024
!truck24.registrationState := #NH
!truck24.licensePlateNumber := 'NH9999'
!truck24.vehicleTypeCode := #TRUCK24
!truck24.registrationLastMaintenanceDate := Date('2024-01-03')
!truck24.expirationDate := Date('2025-01-03')
!truck24.odometerReading := 120000
!truck24.gasTankCapacity := 62.5
!truck24.workingRadio := false
!truck24.mileage := 20

!new RentalAgreement('rentalAgreement24')
!rentalAgreement24.number := 5024
!rentalAgreement24.rentalDate := Date('2025-11-20')
!rentalAgreement24.anticipatedDuration := 4
!rentalAgreement24.depositPaid := 220.0
!rentalAgreement24.quotedDailyRate := 78.0
!rentalAgreement24.quotedRatePerMile := 0.43

!new Individual('individual13')
!individual13.name := 'Lucy Hill'
!individual13.address := '567 Birch Ave, NH'
!individual13.poorRisk := true
!individual13.homePhone := '603-555-7894'
!individual13.driverLicenseState := #NH
!individual13.driverLicenseNumber := 212343121
!individual13.driverLicenseExpirationDate := Date('2030-06-15')

!insert (rentalOffice24, vehicle24) into RentalOfficeVehicle
!insert (rentalOffice24, truck24) into RentalOfficeVehicle

!insert (rentalOffice24, rentalAgreement24) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice9, rentalAgreement24) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement24, truck24) into RentalAgreementVehicle

!insert (rentalAgreement24, individual13) into RentalAgreementCustomer
```
## Generation 23 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#ME' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `ME'.
```
```
<input>:1:0: generation of expression `#NH' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NH'.
```
```
<input>:1:0: generation of expression `#NH' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `NH'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement24' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
567 Birch Ave, NH
```

# Generation 24
```
!new RentalOffice('rentalOffice25')
!rentalOffice25.name := 'Central Rentals'
!rentalOffice25.number := 2525
!rentalOffice25.address := '200 City Hub Ave, MN'

!new Vehicle('vehicle25')
!vehicle25.id := 1025
!vehicle25.registrationState := #MN
!vehicle25.licensePlateNumber := 'MN5555'
!vehicle25.vehicleTypeCode := #COVERED_TRAILER
!vehicle25.registrationLastMaintenanceDate := Date('2023-11-11')
!vehicle25.expirationDate := Date('2024-11-11')

!new Truck('truck25')
!truck25.id := 2025
!truck25.registrationState := #WI
!truck25.licensePlateNumber := 'WI2222'
!truck25.vehicleTypeCode := #TRUCK
!truck25.registrationLastMaintenanceDate := Date('2024-02-25')
!truck25.expirationDate := Date('2025-02-25')
!truck25.odometerReading := 68000
!truck25.gasTankCapacity := 72.0
!truck25.workingRadio := true
!truck25.mileage := 22

!new RentalAgreement('rentalAgreement25')
!rentalAgreement25.number := 5025
!rentalAgreement25.rentalDate := Date('2025-12-01')
!rentalAgreement25.anticipatedDuration := 6
!rentalAgreement25.depositPaid := 400.0
!rentalAgreement25.quotedDailyRate := 110.0
!rentalAgreement25.quotedRatePerMile := 0.38

!new Company('company13')
!company13.name := 'Midwest Logistics'
!company13.address := '800 Maple St, WI'
!company13.poorRisk := false
!company13.idNumber := 345654345

!insert (rentalOffice25, vehicle25) into RentalOfficeVehicle
!insert (rentalOffice25, truck25) into RentalOfficeVehicle

!insert (rentalOffice25, rentalAgreement25) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice20, rentalAgreement25) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement25, vehicle25) into RentalAgreementVehicle

!insert (rentalAgreement25, company13) into RentalAgreementCustomer
```
## Generation 24 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#MN' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `MN'.
```
```
<input>:1:0: generation of expression `#WI' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WI'.
```
```
<input>:1:0: Variable `rentalOffice20' in expression `rentalOffice20' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement25' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
200 City Hub Ave, MN
```

# Generation 25
```
!new RentalOffice('rentalOffice26')
!rentalOffice26.name := 'MetroCity Rentals'
!rentalOffice26.number := 2626
!rentalOffice26.address := '100 Metropolitan Ave, GA'

!new Vehicle('vehicle26')
!vehicle26.id := 1026
!vehicle26.registrationState := #GA
!vehicle26.licensePlateNumber := 'GA6767'
!vehicle26.vehicleTypeCode := #TRUCK
!vehicle26.registrationLastMaintenanceDate := Date('2023-06-15')
!vehicle26.expirationDate := Date('2024-06-15')

!new Truck('truck26')
!truck26.id := 2026
!truck26.registrationState := #SC
!truck26.licensePlateNumber := 'SC5656'
!truck26.vehicleTypeCode := #TRUCK24
!truck26.registrationLastMaintenanceDate := Date('2024-04-01')
!truck26.expirationDate := Date('2025-04-01')
!truck26.odometerReading := 40000
!truck26.gasTankCapacity := 60.0
!truck26.workingRadio := false
!truck26.mileage := 15

!new RentalAgreement('rentalAgreement26')
!rentalAgreement26.number := 5026
!rentalAgreement26.rentalDate := Date('2025-10-10')
!rentalAgreement26.anticipatedDuration := 5
!rentalAgreement26.depositPaid := 275.0
!rentalAgreement26.quotedDailyRate := 90.0
!rentalAgreement26.quotedRatePerMile := 0.33

!new Individual('individual14')
!individual14.name := 'James Carter'
!individual14.address := '123 Olive St, SC'
!individual14.poorRisk := false
!individual14.homePhone := '803-555-2323'
!individual14.driverLicenseState := #SC
!individual14.driverLicenseNumber := 990099009
!individual14.driverLicenseExpirationDate := Date('2027-05-23')

!insert (rentalOffice26, vehicle26) into RentalOfficeVehicle
!insert (rentalOffice26, truck26) into RentalOfficeVehicle

!insert (rentalOffice26, rentalAgreement26) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice15, rentalAgreement26) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement26, truck26) into RentalAgreementVehicle

!insert (rentalAgreement26, individual14) into RentalAgreementCustomer
```
## Generation 25 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `SC'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `SC'.
```
```
<input>:1:0: Variable `rentalOffice15' in expression `rentalOffice15' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement26' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 1 | 2 | 50.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

| Invalid Addresses | 
|---| 
```
100 Metropolitan Ave, GA
```

# Generation 26
```
!new RentalOffice('rentalOffice27')
!rentalOffice27.name := 'Sunset Rentals'
!rentalOffice27.number := 2727
!rentalOffice27.address := '989 Sunset Blvd, NV'

!new Vehicle('vehicle27')
!vehicle27.id := 1027
!vehicle27.registrationState := #NV
!vehicle27.licensePlateNumber := 'NV7878'
!vehicle27.vehicleTypeCode := #OPEN_TRAILER
!vehicle27.registrationLastMaintenanceDate := Date('2023-09-25')
!vehicle27.expirationDate := Date('2024-09-25')

!new Truck('truck27')
!truck27.id := 2027
!truck27.registrationState := #CA
!truck27.licensePlateNumber := 'CA4545'
!truck27.vehicleTypeCode := #TRUCK10
!truck27.registrationLastMaintenanceDate := Date('2024-03-18')
!truck27.expirationDate := Date('2025-03-18')
!truck27.odometerReading := 30000
!truck27.gasTankCapacity := 50.0
!truck27.workingRadio := true
!truck27.mileage := 14

!new RentalAgreement('rentalAgreement27')
!rentalAgreement27.number := 5027
!rentalAgreement27.rentalDate := Date('2025-08-18')
!rentalAgreement27.anticipatedDuration := 3
!rentalAgreement27.depositPaid := 195.0
!rentalAgreement27.quotedDailyRate := 85.0
!rentalAgreement27.quotedRatePerMile := 0.30

!new Company('company14')
!company14.name := 'Desert Transport Solutions'
!company14.address := '456 Oasis Ln, CA'
!company14.poorRisk := false
!company14.idNumber := 8787878787

!insert (rentalOffice27, vehicle27) into RentalOfficeVehicle
!insert (rentalOffice27, truck27) into RentalOfficeVehicle

!insert (rentalOffice27, rentalAgreement27) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice21, rentalAgreement27) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement27, truck27) into RentalAgreementVehicle

!insert (rentalAgreement27, company14) into RentalAgreementCustomer
```
## Generation 26 summary
| General | Value | 
|---|---| 
| Syntax Errors | 4 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NV'.
```
```
INTERNAL ERROR: An unexpected exception occurred. This happened most probably
```
```
<input>:1:0: Variable `rentalOffice21' in expression `rentalOffice21' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement27' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
989 Sunset Blvd, NV
```
```
456 Oasis Ln, CA
```

# Generation 27
```
!new RentalOffice('rentalOffice28')
!rentalOffice28.name := 'Ocean Breeze Rentals'
!rentalOffice28.number := 2828
!rentalOffice28.address := '101 Coastal Ln, FL'

!new Vehicle('vehicle28')
!vehicle28.id := 1028
!vehicle28.registrationState := #FL
!vehicle28.licensePlateNumber := 'FL9090'
!vehicle28.vehicleTypeCode := #COVERED_TRAILER
!vehicle28.registrationLastMaintenanceDate := Date('2023-08-05')
!vehicle28.expirationDate := Date('2024-08-05')

!new Truck('truck28')
!truck28.id := 2028
!truck28.registrationState := #GA
!truck28.licensePlateNumber := 'GA8989'
!truck28.vehicleTypeCode := #TRUCK24
!truck28.registrationLastMaintenanceDate := Date('2024-06-12')
!truck28.expirationDate := Date('2025-06-12')
!truck28.odometerReading := 47000
!truck28.gasTankCapacity := 58.0
!truck28.workingRadio := false
!truck28.mileage := 9

!new RentalAgreement('rentalAgreement28')
!rentalAgreement28.number := 5028
!rentalAgreement28.rentalDate := Date('2025-11-11')
!rentalAgreement28.anticipatedDuration := 2
!rentalAgreement28.depositPaid := 250.0
!rentalAgreement28.quotedDailyRate := 65.0
!rentalAgreement28.quotedRatePerMile := 0.48

!new Individual('individual15')
!individual15.name := 'Ava Johnson'
!individual15.address := '789 Pearl Ave, SC'
!individual15.poorRisk := true
!individual15.homePhone := '843-555-5678'
!individual15.driverLicenseState := #SC
!individual15.driverLicenseNumber := 555444333
!individual15.driverLicenseExpirationDate := Date('2027-09-20')

!insert (rentalOffice28, vehicle28) into RentalOfficeVehicle
!insert (rentalOffice28, truck28) into RentalOfficeVehicle

!insert (rentalOffice28, rentalAgreement28) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice11, rentalAgreement28) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement28, truck28) into RentalAgreementVehicle

!insert (rentalAgreement28, individual15) into RentalAgreementCustomer
```
## Generation 27 summary
| General | Value | 
|---|---| 
| Syntax Errors | 5 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `SC'.
```
```
<input>:1:0: Variable `rentalOffice11' in expression `rentalOffice11' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement28' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 2 | 2 | 100.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

# Generation 28
```
!new RentalOffice('rentalOffice29')
!rentalOffice29.name := 'Greenfield Rentals'
!rentalOffice29.number := 2929
!rentalOffice29.address := '234 Emerald Rd, OR'

!new Vehicle('vehicle29')
!vehicle29.id := 1029
!vehicle29.registrationState := #OR
!vehicle29.licensePlateNumber := 'OR1234'
!vehicle29.vehicleTypeCode := #TRUCK24
!vehicle29.registrationLastMaintenanceDate := Date('2023-10-30')
!vehicle29.expirationDate := Date('2024-10-30')

!new Truck('truck29')
!truck29.id := 2029
!truck29.registrationState := #WA
!truck29.licensePlateNumber := 'WA5678'
!truck29.vehicleTypeCode := #TRUCK10
!truck29.registrationLastMaintenanceDate := Date('2024-07-01')
!truck29.expirationDate := Date('2025-07-01')
!truck29.odometerReading := 55000
!truck29.gasTankCapacity := 61.0
!truck29.workingRadio := true
!truck29.mileage := 7

!new RentalAgreement('rentalAgreement29')
!rentalAgreement29.number := 5029
!rentalAgreement29.rentalDate := Date('2026-01-20')
!rentalAgreement29.anticipatedDuration := 7
!rentalAgreement29.depositPaid := 380.0
!rentalAgreement29.quotedDailyRate := 95.0
!rentalAgreement29.quotedRatePerMile := 0.32

!new Company('company15')
!company15.name := 'Evergreen Transport LLC'
!company15.address := '123 Forest Ln, WA'
!company15.poorRisk := false
!company15.idNumber := 7070707070

!insert (rentalOffice29, vehicle29) into RentalOfficeVehicle
!insert (rentalOffice29, truck29) into RentalOfficeVehicle

!insert (rentalOffice29, rentalAgreement29) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice22, rentalAgreement29) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement29, vehicle29) into RentalAgreementVehicle

!insert (rentalAgreement29, company15) into RentalAgreementCustomer
```
## Generation 28 summary
| General | Value | 
|---|---| 
| Syntax Errors | 6 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `OR'.
```
```
<input>:1:0: generation of expression `#WA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WA'.
```
```
INTERNAL ERROR: An unexpected exception occurred. This happened most probably
```
```
<input>:1:0: Variable `rentalOffice22' in expression `rentalOffice22' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement29' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 2 | 2 | 100.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

# Generation 29
```
!new RentalOffice('rentalOffice30')
!rentalOffice30.name := 'Riverside Rentals'
!rentalOffice30.number := 3030
!rentalOffice30.address := '789 Riverbend Dr, TN'

!new Vehicle('vehicle30')
!vehicle30.id := 1030
!vehicle30.registrationState := #KY
!vehicle30.licensePlateNumber := 'KY7654'
!vehicle30.vehicleTypeCode := #OPEN_TRAILER
!vehicle30.registrationLastMaintenanceDate := Date('2024-02-15')
!vehicle30.expirationDate := Date('2025-02-15')

!new Truck('truck30')
!truck30.id := 2030
!truck30.registrationState := #TN
!truck30.licensePlateNumber := 'TN9090'
!truck30.vehicleTypeCode := #TRUCK
!truck30.registrationLastMaintenanceDate := Date('2024-05-05')
!truck30.expirationDate := Date('2025-05-05')
!truck30.odometerReading := 8000
!truck30.gasTankCapacity := 53.0
!truck30.workingRadio := false
!truck30.mileage := 15

!new RentalAgreement('rentalAgreement30')
!rentalAgreement30.number := 5030
!rentalAgreement30.rentalDate := Date('2026-03-10')
!rentalAgreement30.anticipatedDuration := 12
!rentalAgreement30.depositPaid := 700.0
!rentalAgreement30.quotedDailyRate := 105.0
!rentalAgreement30.quotedRatePerMile := 0.40

!new Individual('individual16')
!individual16.name := 'Emma Thompson'
!individual16.address := '321 Bluegrass Ln, KY'
!individual16.poorRisk := false
!individual16.homePhone := '859-555-1212'
!individual16.driverLicenseState := #KY
!individual16.driverLicenseNumber := 123123123
!individual16.driverLicenseExpirationDate := Date('2031-11-10')

!insert (rentalOffice30, vehicle30) into RentalOfficeVehicle
!insert (rentalOffice30, truck30) into RentalOfficeVehicle

!insert (rentalOffice30, rentalAgreement30) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice9, rentalAgreement30) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement30, truck30) into RentalAgreementVehicle

!insert (rentalAgreement30, individual16) into RentalAgreementCustomer
```
## Generation 29 summary
| General | Value | 
|---|---| 
| Syntax Errors | 7 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#KY' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `KY'.
```
```
<input>:1:0: generation of expression `#TN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `TN'.
```
```
<input>:1:0: generation of expression `#KY' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `KY'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement30' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 2 | 2 | 100.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 1 | 1 | 100.00% |

# Generation 30
```
!new RentalOffice('rentalOffice31')
!rentalOffice31.name := 'Canyon Rentals'
!rentalOffice31.number := 3131
!rentalOffice31.address := '456 Desert Canyon Rd, UT'

!new Vehicle('vehicle31')
!vehicle31.id := 1031
!vehicle31.registrationState := #CO
!vehicle31.licensePlateNumber := 'CO9080'
!vehicle31.vehicleTypeCode := #TRUCK
!vehicle31.registrationLastMaintenanceDate := Date('2024-04-18')
!vehicle31.expirationDate := Date('2025-04-18')

!new Truck('truck31')
!truck31.id := 2031
!truck31.registrationState := #UT
!truck31.licensePlateNumber := 'UT5656'
!truck31.vehicleTypeCode := #TRUCK24
!truck31.registrationLastMaintenanceDate := Date('2024-02-22')
!truck31.expirationDate := Date('2025-02-22')
!truck31.odometerReading := 35000
!truck31.gasTankCapacity := 68.0
!truck31.workingRadio := true
!truck31.mileage := 17

!new RentalAgreement('rentalAgreement31')
!rentalAgreement31.number := 5031
!rentalAgreement31.rentalDate := Date('2026-05-15')
!rentalAgreement31.anticipatedDuration := 9
!rentalAgreement31.depositPaid := 480.0
!rentalAgreement31.quotedDailyRate := 90.0
!rentalAgreement31.quotedRatePerMile := 0.35

!new Company('company16')
!company16.name := 'Rocky Transport Inc.'
!company16.address := '789 Plateau Blvd, CO'
!company16.poorRisk := true
!company16.idNumber := 1616161616

!insert (rentalOffice31, vehicle31) into RentalOfficeVehicle
!insert (rentalOffice31, truck31) into RentalOfficeVehicle

!insert (rentalOffice31, rentalAgreement31) into RentalOfficeRentalAgreementOrigin

!insert (rentalOffice10, rentalAgreement31) into RentalOfficeRentalAgreementDrop

!insert (rentalAgreement31, vehicle31) into RentalAgreementVehicle

!insert (rentalAgreement31, company16) into RentalAgreementCustomer
```
## Generation 30 summary
| General | Value | 
|---|---| 
| Syntax Errors | 3 | 
| Multiplicities Errors | 1 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `UT'.
```
```
<input>:1:0: Variable `rentalOffice10' in expression `rentalOffice10' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement31' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 0 | 2 | 0.00% |
| License Plates | 2 | 2 | 100.00% |
| Home Phones | 0 | 0 | 0.00% |

| Invalid Addresses | 
|---| 
```
456 Desert Canyon Rd, UT
```
```
789 Plateau Blvd, CO
```

# Summary for all generations
| Summary | Value | 
|---|---| 
| Model | GPT_4O | 
| Type | Simple | 
| System | vehiclerental | 
| Number of generations | 30 | 

| General | Value | 
|---|---| 
| Syntax Errors | 133 | 
| Multiplicities Errors | 29 | 
| Invariants Errors | 0 | 

| Syntax Errors | 
|---| 
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```
```
<input>:1:0: generation of expression `#NY' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `NY'.
```
```
<input>:1:0: Variable `rentalOffice3' in expression `rentalOffice3' is undefined.
```
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:31: Undefined enumeration literal `NV'.
```
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `TX'.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice4' in expression `rentalOffice4' is undefined.
```
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `UT'.
```
```
<input>:1:0: Variable `rentalOffice2' in expression `rentalOffice2' is undefined.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice6' in expression `rentalOffice6' is undefined.
```
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:29: Undefined enumeration literal `TX'.
```
```
<input>:1:0: Variable `rentalOffice5' in expression `rentalOffice5' is undefined.
```
```
<input>:1:0: Variable `rentalOffice7' in expression `rentalOffice7' is undefined.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#TN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `TN'.
```
```
<input>:1:0: Variable `rentalOffice3' in expression `rentalOffice3' is undefined.
```
```
<input>:1:0: generation of expression `#DC' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `DC'.
```
```
<input>:1:0: generation of expression `#NC' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NC'.
```
```
<input>:1:0: generation of expression `#WV' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `WV'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```
```
<input>:1:0: generation of expression `#VA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `VA'.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `GA'.
```
```
<input>:1:0: Variable `rentalOffice10' in expression `rentalOffice10' is undefined.
```
```
<input>:1:0: generation of expression `#NY' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NY'.
```
```
<input>:1:0: generation of expression `#MA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `MA'.
```
```
<input>:1:0: Variable `rentalOffice1' in expression `rentalOffice1' is undefined.
```
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `OR'.
```
```
<input>:1:0: generation of expression `#WA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WA'.
```
```
<input>:1:0: Variable `rentalOffice8' in expression `rentalOffice8' is undefined.
```
```
<input>:1:0: generation of expression `#TX' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `TX'.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:35: Undefined enumeration literal `GA'.
```
```
<input>:1:0: Variable `rentalOffice12' in expression `rentalOffice12' is undefined.
```
```
<input>:1:0: generation of expression `#NJ' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NJ'.
```
```
<input>:1:0: generation of expression `#PA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `PA'.
```
```
<input>:1:0: Variable `rentalOffice14' in expression `rentalOffice14' is undefined.
```
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NM'.
```
```
<input>:1:0: generation of expression `#LA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `LA'.
```
```
<input>:1:0: Variable `rentalOffice5' in expression `rentalOffice5' is undefined.
```
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `UT'.
```
```
<input>:1:0: generation of expression `#WY' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WY'.
```
```
<input>:1:0: Variable `rentalOffice7' in expression `rentalOffice7' is undefined.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NV'.
```
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `NM'.
```
```
<input>:1:0: Variable `rentalOffice18' in expression `rentalOffice18' is undefined.
```
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `OR'.
```
```
<input>:1:0: Variable `rentalOffice16' in expression `rentalOffice16' is undefined.
```
```
<input>:1:0: generation of expression `#IL' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `IL'.
```
```
<input>:1:0: generation of expression `#IN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `IN'.
```
```
<input>:1:0: generation of expression `#IN' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `IN'.
```
```
<input>:1:0: Variable `rentalOffice13' in expression `rentalOffice13' is undefined.
```
```
<input>:1:0: generation of expression `#NM' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NM'.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NV'.
```
```
<input>:1:0: Variable `rentalOffice19' in expression `rentalOffice19' is undefined.
```
```
<input>:1:0: generation of expression `#ME' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `ME'.
```
```
<input>:1:0: generation of expression `#NH' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `NH'.
```
```
<input>:1:0: generation of expression `#NH' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `NH'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```
```
<input>:1:0: generation of expression `#MN' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `MN'.
```
```
<input>:1:0: generation of expression `#WI' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WI'.
```
```
<input>:1:0: Variable `rentalOffice20' in expression `rentalOffice20' is undefined.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `SC'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `SC'.
```
```
<input>:1:0: Variable `rentalOffice15' in expression `rentalOffice15' is undefined.
```
```
<input>:1:0: generation of expression `#NV' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `NV'.
```
```
INTERNAL ERROR: An unexpected exception occurred. This happened most probably
```
```
<input>:1:0: Variable `rentalOffice21' in expression `rentalOffice21' is undefined.
```
```
<input>:1:0: generation of expression `#GA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `GA'.
```
```
<input>:1:0: generation of expression `#SC' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `SC'.
```
```
<input>:1:0: Variable `rentalOffice11' in expression `rentalOffice11' is undefined.
```
```
<input>:1:0: generation of expression `#OR' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `OR'.
```
```
<input>:1:0: generation of expression `#WA' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `WA'.
```
```
INTERNAL ERROR: An unexpected exception occurred. This happened most probably
```
```
<input>:1:0: Variable `rentalOffice22' in expression `rentalOffice22' is undefined.
```
```
<input>:1:0: generation of expression `#KY' failed, with following error:
```
```
<input>:1:32: Undefined enumeration literal `KY'.
```
```
<input>:1:0: generation of expression `#TN' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `TN'.
```
```
<input>:1:0: generation of expression `#KY' failed, with following error:
```
```
<input>:1:36: Undefined enumeration literal `KY'.
```
```
<input>:1:0: Variable `rentalOffice9' in expression `rentalOffice9' is undefined.
```
```
<input>:1:0: generation of expression `#UT' failed, with following error:
```
```
<input>:1:30: Undefined enumeration literal `UT'.
```
```
<input>:1:0: Variable `rentalOffice10' in expression `rentalOffice10' is undefined.
```

| Multiplicities Errors | 
|---| 
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement3' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement4' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement5' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement6' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement7' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement8' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement9' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement10' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement11' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement12' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement13' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement14' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement15' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement16' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement17' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement18' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement19' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement20' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement21' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement22' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement23' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement24' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement25' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement26' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement27' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement28' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement29' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement30' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```
```
Multiplicity constraint violation in association `RentalOfficeRentalAgreementDrop':
  Object `rentalAgreement31' of class `RentalAgreement' is connected to 0 objects of class `RentalOffice'
  at association end `droppoffRentalOffice' but the multiplicity is specified as `1'.
```

| VehicleRental | Valid | Total | Success (%) | 
|---|---|---|---| 
| Addresses | 30 | 63 | 47.62% |
| License Plates | 62 | 62 | 100.00% |
| Home Phones | 16 | 16 | 100.00% |

| Invalid Addresses | 
|---| 
```
202 Silicon St, CA
```
```
456 Industrial Way, AZ
```
```
321 City Center Blvd, CT
```
```
1122 Distribution Way, AL
```
```
303 Aviation Ln, AZ
```
```
789 Cliffside Rd, CO
```
```
400 Downtown Cir, AZ
```
```
200 Eco Blvd, CA
```
```
123 Maple Ln, AZ
```
```
1500 Industry Pkwy, AL
```
```
456 Logistics Ave, TX
```
```
900 Constitution Ave, DC
```
```
1600 Oceanview Blvd, FL
```
```
880 Harbor Lane, NY
```
```
222 Central Park Ave, NY
```
```
555 Expressway St, CA
```
```
123 Rapid Rd, NV
```
```
456 Broadway, NY
```
```
800 Timber St, AL
```
```
456 Summit Blvd, NV
```
```
500 Desert Way, AZ
```
```
333 Sun Blvd, NM
```
```
456 Wave Ave, WA
```
```
123 Edge Pkwy, IL
```
```
101 Lakeview Dr, IN
```
```
555 Sand Dunes Ave, AZ
```
```
567 Birch Ave, NH
```
```
200 City Hub Ave, MN
```
```
100 Metropolitan Ave, GA
```
```
989 Sunset Blvd, NV
```
```
456 Oasis Ln, CA
```
```
456 Desert Canyon Rd, UT
```
```
789 Plateau Blvd, CO
```

