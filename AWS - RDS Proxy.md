![image](https://github.com/nhvu95/aws-handbook/assets/26276890/f4fac5da-52cc-4d98-8d20-a1cc8448cb06)

## AWS - RDS Proxy
* Fully managed database proxy for RDS
* Allows apps to pool and share DB connections establish with the database
* Improving database efficiency by reducing the stress on database resources (e.g CPU, RAM) and minimize open connections (and timeouts)
* Serverless, autoscaling, highly available (multi-AZ)
* Reduce RDS & Aurora failover time by up to 66%
* Supports RDS (MySQL, PostgreSQL, MariaDB, MSSQL Server) and Aurora (MySQL, PostgreSQL)
* No code changes required for most apps
* Enfore IAM Authentication for DB, and securely store credentials in AWS Secrets Manager
* RDS Proxy is never publicly accessible (must be accessed from VPC)
