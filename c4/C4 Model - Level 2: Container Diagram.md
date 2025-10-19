# C4 Model - Level 2: Container Diagram

## Overview
High-level technical architecture showing major containers and their interactions.

## Container Architecture

```
                           [Load Balancer]
                                 |
                    +------------+------------+
                    |            |            |
            [Web Application] [Mobile App] [Technician App]
                    |            |            |
                    +------------+------------+
                                 |
                          [API Gateway]
                                 |
        +------------------------+------------------------+
        |           |            |            |           |
[Booking Service] [Fleet Service] [User Service] [Payment Service]
        |           |            |            |           |
        +------------------------+------------------------+
                                 |
                        [Event Streaming Bus]
                                 |
        +------------------------+------------------------+
        |            |           |            |           |
[Analytics Engine] [AI/ML Platform] [Notification Service] [Audit Service]
        |            |           |            |           |
        +------------------------+------------------------+
                                 |
                    +------------+------------+
                    |            |            |
            [Operational DB] [Analytics DB] [Object Storage]
```

## Container Descriptions

### Frontend Containers
1. **Web Application** (React/Next.js)
   - Customer portal for desktop users
   - Corporate administration interface
   - Real-time booking and fleet visualization

2. **Mobile Application** (React Native)
   - Primary customer interface
   - NFC vehicle unlocking
   - Photo capture for returns
   - Offline capability with sync

3. **Technician Application** (React Native)
   - Fleet maintenance interface
   - Route optimization display
   - Work order management
   - Battery inventory tracking

### API Layer
4. **API Gateway**
   - Request routing and load balancing
   - Authentication and authorization
   - Rate limiting and throttling
   - API versioning

### Core Services
5. **Booking Service**
   - Reservation management
   - Availability checking
   - Carpooling matching
   - Subscription handling

6. **Fleet Service**
   - Vehicle tracking and telemetry
   - Remote lock/unlock control
   - Maintenance scheduling
   - Redistribution planning

7. **User Service**
   - User profile management
   - Risk scoring
   - Authentication/authorization
   - Corporate account management

8. **Payment Service**
   - Payment processing
   - Dynamic pricing calculation
   - Fine management
   - Billing and invoicing

### Event-Driven Layer
9. **Event Streaming Bus**
   - Real-time event distribution
   - Service decoupling
   - Event sourcing
   - Audit trail

### AI/Analytics Containers
10. **Analytics Engine**
    - Real-time analytics processing
    - KPI calculation
    - Business intelligence
    - Reporting

11. **AI/ML Platform**
    - Demand prediction models
    - Computer vision for returns
    - Fraud detection
    - Route optimization
    - Predictive maintenance

12. **Notification Service**
    - Push notifications
    - SMS/Email delivery
    - In-app messaging
    - Alert management

13. **Audit Service**
    - Transaction logging
    - Compliance reporting
    - Security event tracking
    - Data retention

### Data Stores
14. **Operational Database** (PostgreSQL with sharding)
    - Transactional data
    - User profiles
    - Active bookings
    - Fleet status

15. **Analytics Database** (Time-series optimized)
    - Historical data
    - Telemetry data
    - Usage patterns
    - Performance metrics

16. **Object Storage**
    - Return photos
    - ML models
    - Documents
    - Backups

## Key Technology Choices
- **Communication**: REST for synchronous, event streaming for async
- **Security**: OAuth 2.0/JWT for authentication
- **Deployment**: Containerized microservices on Kubernetes
- **Monitoring**: Distributed tracing and centralized logging
- **Data**: Polyglot persistence based on use case