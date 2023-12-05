![image](https://github.com/nhvu95/aws-handbook/assets/26276890/70c3636e-23ca-46d5-b674-d5c74a8f8fb2)

## AWS - RDS - Amazon RDS Overview
- RDS stands for Relational Database Service
- It's a managed DB service for DB uses SQL as a query language.
- It allows you to create databases in the cloud that are managed by AWS
  - Postgres
  - MySQL
  - MariaDB
  - Oracle
  - Microsoft SQL Server
  - Aurora (AWS Proprietary database)

### I. The advantage of using RDS versus deploying DB on EC2
* RDS is a managed service
  - Automated provisioning, OS patching
  - Continuous backups and restore to specific timestamps (Point in Time Restore)!
  - Monitoring dashboards
  - Read replicas for improved read performance
  - Multi-AZ setup for DR (Disaster Recovery)
  - Maintenance windows for upgrades
  - Scaling capability (vertical and horizontal)
  - Storage backed by EBS ( gp2 or io1)
* But you can't SSH into your instances

### II. RDS - Store Auto Scaling
* Help you increase storage on your RDS DB instance dynamically
* When RDS detects you are running out of free database storage, it scales automatically.
* Avoid manually scaling your database storage
* You have to set Maximum storage Threshold (maximum limit for DB storage)
* Automatically modify storage if:
       - Free storage is less than 10% of allocated storage
       - Low-storage lasts at least 5 minutes.
       - 6 hours have passed since the last modification.
* Useful for applications with unpredictable workloads
* Supports all RDS database engines (MariaDB, MySQL, PostgreSQL, SQL Server, Oracle)
