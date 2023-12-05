

## RDS Backups
* Automated backups:
   - Daily full backup of the database (during the backup window)
   - Transaction logs are backed up by RDS every 5 minutes
   => ability to restore to any point in time ( from oldest backup to 5 minutes ago)
   - 1 to 35 days of retention, set 0 to disable automated backups
* Manual DB snapshots
   - Manually triggered by the user
   - Retention of backup for as long as you want

* Trick: in a stopped RDS database, you will still pay for storage; if you plan on stopping it for a long time, you should snapshot & restore instead

### I. Aurora Backups
* Automated backups
      - 1 to 35 days ( cannot be disabled)
      - Point in time recovery in that timeframe
* Manual DB snapshots
      - Manually triggered by the user
      - Retention of backup for as long as you want

### II. RDS & Aurora restore options
* Restoring a RDS / Aurora backup or a snapshot creates a new database
* Restore MySQL RDS database from s3 
      - Create a backup of your on-premises database
      - Store it on Amazon S3 (object storage)
      - Restore the backup file onto a new RDS instance running MySQL
* Restoring MySQL Aurora cluster from S3
   - Create a backup of your on-premise database using Percona XtraBackup
   - Store the backup file on Amazon S3
   - Restore the backup file onto a new Aurora cluster running MySQL

### III. Aurora database cloning
* Create a new Aurora DB Cluster from an existing one
* Faster than snapshot & restore

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/3e33e4f3-4e07-4189-87de-29da20debdf6)
* Use copy-on-write protocol
     - Initially, the new DB cluster uses the same data volume as the original DB cluster (fast and efficient - no copying is needed)
     - When updates are made to the new DB Cluster data, then additional storage is allocated, and data is copied to be separated
* Very fast & cost-effective
* Useful to create a "staging" database from a "production" database without impacting the production database
