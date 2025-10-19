# C4 Model - Level 1: System Context

## Overview
The MobilityCorp System provides short-term vehicle rental services with AI-powered optimization for fleet management and user experience.

## System Context Diagram

```
[Customer] --uses--> [MobilityCorp Platform]
[Technician] --maintains fleet--> [MobilityCorp Platform]
[Chauffeur] --provides services--> [MobilityCorp Platform]
[Corporate Admin] --manages accounts--> [MobilityCorp Platform]

[MobilityCorp Platform] --integrates--> [Payment Gateway]
[MobilityCorp Platform] --uses--> [Government ID Verification]
[MobilityCorp Platform] --uses--> [Mapping Services]
[MobilityCorp Platform] --uses--> [Weather Services]
[MobilityCorp Platform] --integrates--> [Vehicle Telematics]
[MobilityCorp Platform] --uses--> [Insurance Provider]
[MobilityCorp Platform] --integrates--> [Municipal Parking Systems]
[MobilityCorp Platform] --uses--> [SMS/Email Services]
```

## Actors

### Primary Users
- **Customer**: End users who rent vehicles (bikes, scooters, cars, vans)
- **Technician**: Fleet maintenance staff who swap batteries and service vehicles
- **Chauffeur**: Professional drivers for chauffeur service
- **Corporate Admin**: Manages corporate accounts and bulk bookings

### External Systems
- **Payment Gateway**: Processes payments and deposits
- **Government ID Verification**: Validates user identity and driving licenses
- **Mapping Services**: Provides navigation and location services
- **Weather Services**: Supplies weather data for demand prediction
- **Vehicle Telematics**: Direct integration with vehicle hardware
- **Insurance Provider**: Validates coverage and processes claims
- **Municipal Parking Systems**: Integrates with city parking infrastructure
- **SMS/Email Services**: Handles notifications and communications

## Key Interactions

1. **Customer Journey**
   - Registration with ID verification
   - Vehicle discovery and booking
   - Unlocking via NFC
   - Return with photo verification
   - Payment processing

2. **Fleet Management**
   - Real-time vehicle tracking
   - Predictive maintenance
   - Battery swap optimization
   - Redistribution planning

3. **AI-Powered Services**
   - Demand prediction
   - Dynamic pricing
   - Fraud detection
   - Route optimization