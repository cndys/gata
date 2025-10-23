# ADR-007: Object Storage (S3) for Media Files and Data Lake Storage

## Status
Accepted

## Context

Our platform generates and processes several types of large files:
- User photos and documents (binary format)
- Delta Lake tables for metrics and batch 

Requirements include:
- Scalable and cost-effective storage
- High availability and durability
- Performant access from different services

## Decision

Adopt MinIO (S3-compatible) as the primary object storage solution:
- **Media Storage**: Photos, documents, uploaded files
- **Data Lake**: Parquet files and Delta Lake tables
- **Analytics**: Historical data and ML datasets

## Consequences

### Positive
- **Scalability**: Near-unlimited and elastic storage
- **Cost-effectiveness**: Pay-per-GB pricing, automatic archiving
- **Durability**
- **Performance**: Parallel and distributed data access

### Negative
- **Latency**
- **Consistency**
- **Network complexity**
- **Transfer costs**

## Alternatives Considered

### NFS/File System
- Pros: Low latency, POSIX interface
- Cons: No horizontal scalability, single point of failure
- Reason for rejection: Incompatible with distributed architecture

### Relational Database
- Pros: ACID transactions, strong consistency
- Cons: Poor performance, size limitations, high cost
- Reason for rejection: Not suitable for large data volumes

### HDFS
- Pros: Optimized for Big Data, Hadoop integration
- Cons: Operational complexity, no standard REST API
- Reason for rejection: S3 is simpler and de facto standard
