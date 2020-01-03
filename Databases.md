# AWS Databases

 #### Relational Databases
 Relational Databases has two key features
 * Multi AZ : Use for Disaster Recovery
 * Read Replicas: For Better Performance
 
 #### Relational Databases in AWS
 * SQL
 * MySQL
 * Postgre SQL
 * Oracle
 * Aurora
 * Maria DB

DyanamoDB is noSQL database.
Redshift is the datawarehouse used in AWS.

#### Elastic-cache
* It is a webservice which makes easy to deploy, operate and scale an in-memory cache in the cloud.
* It is used to speed up performance of existing databases.

#### RDS-Instance
* RDS runs on virtual machines.
* You have no access to RDS machine but Amazon does. Patching and maintaining the operating system is Amazon's job.
* RDS is not serverless.
* Aurora Serverless is serverless.

#### RDS-Back Ups , Multi A-Z and Read Replicas.
 * Backups
    * Automated Backups
    * Database Snapshots
   
 * Read Replicas (Things to Remember)
    * Can be Multi-AZ
    * Used to increase performance
    * Must have backup turned on
    * Can be in different regions
    * Can be MySQL, Postgre SQL, MariaDB, Oracle, Aurora
    * Can be promoted to Master, but this will break the read replica
    
 * Multi A-Z
    * Used for DR (Disaster Recovery)
    * Can force a failover from one AZ to another by rebooting the RDS instance
 
 * Encryption at rest is supported for MySQL, Oracle, SQL server, Postgre SQL, MariaDB and Aurora. Encryption is done using AWS Key Mangement Service (KMS). Once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas and snapshots.
 
#### DynamoDB
* NOSQL database solution ( opposite of RDS)
 ## Basics of DynamoDB are:
     * Stored on SSD storage
     * Spread across 3 geographically distinct data centers.
     * Eventual Consistent Reads ( Default) (app won't read data in first second) 
     * Strongly COnsistent Reads (1 sec or less)

#### Redshift 
- a fast and powerfull, fully manage, petabyte scale data warehouse service in cloud.
OLAP transaction Example:

Redshit can be configured as follows:
- Single Node (160 Gb)
- Multi node
   - Leader node ( manages client connections and receives queries)
   - Compute Node ( Store data and perform queries and computations). Up to 128 Compute nodes.
   
   Backups
   - Enabled by default with a 1 day rentention period
   - Maximum retention period: 35 days
   - Redshift always attempts to maintain at least three copiers of data( original and replica on the compute nodes and a backup in S3)
   - Redshift can also asynchronously replicate snapshots to S3 in another region for disaster recovery.
   
 Redshift priced upon:
 - Compute Node Hours 
 - Backup 
 - Data transfer ( within a VPC)
 
 Security Considerations:
 - Encrypted in transist using SSL
 - Encrypted at rest using AES-256 encryption
 - By default Redshift takes care of key management
 
Availability:
 - Only one 1 AZ
 - Can restore snapshots to new AZ in event of outage.

 
Amazon Aurora:
Things to know about Aurora
- Start with 10 GB, Scales in 10 GB increments to 64TB (Storage Autoscaling)
- Compute resouces can scale upto 32vCPUs and 244GB of Memory.
- 2 copies of your data is contained in each AZ, with minimum of 3 AZ. 6 copies of your data.

Scaling Aurora:
-designed to handle loss of two copies of data without affecting database write availability and up to three copies without affecting read availability.
- Storage is also self-healing. Data blocks and disks are continuously scanned for errors and repaired automatically.

Two types of Aurora Replicas
- Aurora Replicas (15 of them)
- MySQL Read Replicas ( currently 5)

Tips:
- Aurora snapchots can be shared with other AWS accounts.
- Aurora has automated backups turned on by default, You can also take snapshots on aurora.

Elasticache
- webservice that makes it easy to deploy, operate and scale an in-memory cache inthe cloud
The service improves the performence of web applications by allowing you to retrieve infomration
from fast, managed, in-memory caches, instead of relying entirely on slower disk-based databases.

ElasticCache supports two open-source in-memory caching engines:
- Memcached ( simple cache , can be scaled horizontally)
- Redis ( advanced data types, multiple AZs, backup and stores)

- Use Elasticache to increase database and web application performance.
- Redis is Multi-AZ
- You can do backups and restores of Redis.

