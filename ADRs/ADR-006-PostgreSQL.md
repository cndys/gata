# ADR-006: PostgreSQL for Transactional and Operational Data

## Status
Accepted

## Context

Our application requires persistent storage for:
- Transactional data (trips, orders, payments)
- User and account metadata

Requirements include:
- ACID compliance for financial transaction integrity
- Support for complex queries with JOINs
- Advanced indexing and performance optimization
- Point-in-time backup and recovery

## Decision

Adopt PostgreSQL as the primary relational database:
- **Transactional data**: Trip management, fleet management, payments, billing
- **Metadata**: User profiles, configurations, parameters

Configuration with:
- Master-slave replication for high availability
- Date-based partitioning for high-volume tables

## Consequences

### Positive
- **Reliability**: ACID compliance, guaranteed data integrity
- **Performance**: Mature query optimizer, advanced indexing
- **Ecosystem**: Mature tooling, available team expertise
- **Standards**: SQL standard, query portability

### Negative
- **Horizontal scalability**: Complex sharding, limited replication
- **Resources**: High memory consumption

## Alternatives Considered

### MySQL
- Pros: Read performance, mature ecosystem
- Cons: Limited advanced features, less flexible
- Reason for rejection: PostgreSQL richer in features

### Oracle Database
- Pros: Enterprise performance, advanced features
- Cons: High licensing cost, vendor lock-in
- Reason for rejection: Budget

### Cassandra (NoSQL Column)
- Pros: Massive scalability, high availability
- Cons: No JOINs, eventual consistency, complexity
- Reason for rejection: Use case doesn't require this scale
