# ADR-002: Event-Driven Architecture

## Status
Accepted

## Context
MobilityCorp's platform requires:
- Real-time updates across multiple services (vehicle status, bookings, payments)
- Loose coupling between services for independent evolution
- Asynchronous processing for non-critical operations

## Decision
We will implement an event-driven architecture **on some part of our system**
using an event streaming platform as the backbone for inter-service communication.

## Consequences

### Positive
- **Loose Coupling**: Services communicate through events without direct dependencies
- **Real-time Processing**: Events enable immediate reactions to state changes
- **Event Sourcing**: Complete audit trail of all state changes (interesting for legal proof if there are issues with a vehicle)
- **ML Integration**: Continuous data stream for model training and inference

### Negative
- **Eventual Consistency**: Data may be temporarily inconsistent across services
- **Debugging Complexity**: Tracing event flows can be challenging
- **Duplicate Events**: Must handle idempotency

## Alternatives Considered

### Request-Response Only
- **Pros**: Simple, synchronous, immediate consistency
- **Cons**: Tight coupling, scaling challenges, no audit trail

### Database Integration
- **Pros**: Strong consistency, simple queries
- **Cons**: Database becomes bottleneck, tight coupling
