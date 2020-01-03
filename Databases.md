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

