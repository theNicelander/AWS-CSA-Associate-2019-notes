`2019 AWS CSA - Associate notes`
==============================

## Databases
### Key Concepts
* **RDS (OLTP)** - Relational Database Service
    * RDS runs on virtual machines. Can't log into them, Amazon handles updates and patching. 
    * Serverless: Aurora
    * !Serverless: SQL, MySQL, PostgreSQL, Oracle, MariaDB
* **DynamDB**: NoSQL database
    * mobile, web, gaming, ad tech, IoT
    * SSD, low-latency, 3 geo-distinct data centres 
* **Aurora**
    * 2 copies across 3 AZs
    * Can be shared to other AWS accounts
* **RedShift (OLAP)** - Cloud data warehouse
    * Designed for OLAP and BI
    * Column based storage, 3 copies 
* **ElastiCache** - Turn on for increased performance
    * In-memory operations
    * MemCached: Simplicity, scale horizontally
    * Redis: Advanced, more Features , multi-AZ, backup/restore
* **Athena** - Interactive query service 
    * Query S3 using SQL
### General 
* **Backups**
    * Automated & Snapshot
* **Read replicas**
    * Increase performance, must have backups. 
    * Can be multi-az, different regions
    * Aurora or MySQL
* **Types**
    * General Purpose SSD: Low cost general
    * Provisioned IOS SSD: High IO
    * Magnetic: Backwards compatibility