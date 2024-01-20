### EBS volumes
 - One instance(except multi attach io1 and io2)
 - Are locked at the AZ level
 - gp2: IO increase if the disk size increases
 - io1: can increase IO independently
 - To migrate EBS volume across AZ
 - Take a snapshot
 - Restore the snapshot to another AZ
 - EBS backups use IO, and you shouldn't run them while your application is handling a lot of traffic
 - Root EBS volumes of instances get terminated by default if the EC2 instance gets terminated. (You can disable that)


### EFS - Elastic File System
  - Mounting 100s of instances across AZ
  - EFS share website files (WordPress)
  - Only for Linux instances (POSIX)
  - EFS has a higher price point than EBS
  - Can leverage EFS-IA for cost saving
  - Remember EFS vs EBS vs Insance store
