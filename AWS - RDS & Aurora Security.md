* At-rest encryption
     - Database master & replicas encryption using AWS KMS - must be defined as launch time
     - If the master is not encrypted database, go through a DB snapshot & restore as encrypted
     - To encrypt an un-encrypted database, go through a DB snapshot & restore as encrypted
* In-flight encryption: TLS-ready by default, use the AWS TLS root certificates client-side
* IAM Authentication: IAM roles to connect to your database (instead of username/pwd)
* Security Groups: Control Network access to your RDS / Aurora DB
* No SSH Available except on RDS Custom
* Audit Logs can be enabled and sent to CloudWatch Logs for longer retention
