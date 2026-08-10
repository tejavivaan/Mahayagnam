# NFS
- NFS (Network File System) is a protocol that lets multiple servers share the same filesystem over a network.
## What NFS 
- A shared folder accessible by many servers.
- Works like a normal Linux directory (/mnt/appdata).
- Supports POSIX operations: read, write, append, delete.
- Centralized storage accessible over TCP/IP.
## Why applications use NFS
- Shared storage for multiple app servers.
- Stores files: images, PDFs, logs, media, backups.
- Cheaper than database storage.
- Handles large binary files efficiently.
- Simple to mount and use (mount -t nfs server:/path /mnt).
## Typical use cases
- User uploads (images, videos, documents), Build artifacts (Jenkins, GitLab), Application logs, Static content.

# DB
- A database (DB) stores structured, relational, queryable data.
## What a DB 
- A transaction engine.
- Stores structured data in tables.
- Supports fast queries, indexing, joins.
- Provides ACID guarantees (Atomicity, Consistency, Isolation, Durability).
## Why applications use DB
- Structured data: users, orders, transactions.
- Fast search: queries, filters, joins.
- Data integrity: constraints, foreign keys.
- Concurrency: thousands of reads/writes.
- Reliability: backups, replication, failover.
## Typical use cases
- User accounts, Product catalog, Payments, Inventory, Configurations.

# Why do applications use BOTH NFS and DB?
- Because they solve different problems.
- No single system can efficiently handle both structured data and large binary files.

## If you store files in DB → problems
- DB becomes slow.
- Backups become huge.
- Replication becomes heavy.
- Query performance drops.
## If you store structured data in NFS → problems
- No indexing.
- No transactions.
- No concurrency control.
- No relational integrity.
## Final architecture pattern
- Most modern apps follow this:
  - App Servers → DB for structured data
  - App Servers → NFS for file storage
- This separation is intentional and critical for performance, scalability, and cost.

# Is there any alternative for both NFS and DB?
- Alternatives to NFS (File Storage)
  - Object Storage : AWS S3, Azure Blob Storage, Google Cloud Storage
- Alternatives to DB (Structured Data)
  - SQL Databases : MySQL, PostgreSQL, MariaDB, MS SQL Server
  - NoSQL Databases  : MongoDB, Cassandra, DynamoDB, Redis
  - Cloud-managed DBs : Amazon RDS, Azure SQL, Google Cloud SQL
