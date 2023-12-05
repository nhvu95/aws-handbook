## AWS - RDS - Amazon Aurora
- Aurora is a proprietary technology from AWS (Not open sourced)
- Postgres and MySQL are both supported as Aurora DB  (That means your drivers will not work as if Aurora was a Postgres or MySQL Database)
- Aurora is "AWS cloud-optimized" and claims 5x performance improvement over MySQL on RDS, over 3x performance of Postgres on RDS
- Aurora storage automatically grows increments of 10GB, up to 128TB
- Aurora can have up to 15 replicas, and the replication process is faster than MySQL (Sub 10ms replica lag)
- Failover in Aurora is instantaneous. It's high availability native.
- Aurora costs more than RDS (20% more) - but it is more efficient

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/a93919d6-7899-4bb5-a8da-980133584506)
### Aurora High Availability and Read Scaling
* 6 Copies of your data across 3AZ:
  - 4 Copies out of 6 needed for writes
  - 3 copies out of 6 needed for reads
  - Self-healing with peer-to-peer replication (it means when the master is interrupted, one replica can be the master )
  - Storage is striped across 100s of volumes
* One Aurora instance takes writes (master)
* Automated failover for master is less than 30 seconds
* Master + up to 15 Aurora Read replicas serve reads
* Support for Cross Region Replication

### Aurora DB Cluster
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/49a2d5af-294f-4e80-b1a9-453b297e495f)

### Features of Aurora
- Automatic failover
- Backup and Recovery
- Isolation and security
- Industry compliance
- Push-button scaling
- Automated Patching with Zero Downtime
- Advanced Monitoring
- Routine Maintenance
- Backtrack: restore data at any point of time without using backups.
