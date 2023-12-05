![image](https://github.com/nhvu95/aws-handbook/assets/26276890/ea7293a5-d0c2-440d-b9ce-b0482e286054)
### I. RDS Read replicas for reading scalability
* Up to 15 Read Replicas
* Within AZ, CrossAZ or Cross Region
* Replication is ASYNC, so reads are eventually consistent
* Replicas can be promoted to their own DB
* Applications must update the connection string to leverage (tận dụng) read replicas

### II. RDS Read Replicas - Use Cases
* You have a production database that is taking on a normal load
* You want to run a reporting application to run some analytics
* You create a Read Replica to run the new workload there
* The production application is unaffected
* Read replicas are used for SELECT (=read) only kind of statements (not INSERT, UPDATE, DELETE)

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/d6012692-5449-40ba-afd3-065ac7fb4b64)
### III. RDS Read Replicas - Network Cost
* In AWS, there's a network cost when data goes from one AZ to another
* For RDS, Read replicas within the same region. You don't pay that fee.

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/1fb6da43-86eb-4e19-bf85-6fc164d35189)
### IV. RDS Multi-AZ (Disaster Recovery)
* SYNC replication 
* One DNS name - automatic app failover to standby
* Increase availability
* Failover in case of loss of AZ, loss of network, instance or storage failure
* No manual intervention in apps
* Not used for scaling
Note: The Read Replicas will be set as multi-AZ for Disaster Recovery (DR)

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/af41125a-915f-4c01-a30b-3f5b7ef1b9a9)
### V. RDS - From Single AZ - to multi-AZ
* Zero downtime operation (no need to stop the DB)
* Just click on "modify" for the database
* The following happens internally:
      - A snapshot is taken
      - A new DB is restored from the snapshot in a new AZ
      - Synchronization is established between the two databases
