### Managed Oracle and Microsoft SQL Server Database with OS and database customization
- RDS: Automates setup, operation, and scaling of database in AWS
- RDS Custom: Access to underlying database and OS, so you can
  - Configure settings
  - Install patches
  - Enable native features
  -  Access the underlying EC2 instance using SSH or SSM Session Manager
- De-activate Automation Mode to perform your customization. It is better to take a BD snapshot before

### RDS vs RDS Custom
  - RDS: entire database and the OS to be managed by AWS
  - RDS Custom: full admin access to the underlying OS and the database
