## AWS - ElastiCache

* The same way RDS is to get managed Relational Databases
* ElastiCache is to get managed Redis or Memcached
* Caches are in-memory databases with really high performance, low latency

* Helps reduce load off of databases for read intensive workloads
* Helps make your application stateless by pushing your state into elasticcache
* AWS takes care of OS maintenancy / patching, optimizations, setup, configuration, monitoring, failure recovery and backup
* Using ElastiCache involves heavy application code changes


### I. ElastiCache - Solution Architechture - DB Cache
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/37392294-4057-4dca-92ba-ba9dff4a8ba1)
USECASE 1 (PIC 1)
* Applications queries ElastiCache, if not available, get from RDS and store in ElastiCache
* Helps relieve load in RDS
* Cache must have an invalidation strategy to make sure only the most current data is used in there.

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/a65238fb-77f2-4b38-92a1-7d41f3280446)
USECASE 2 (PIC 2)
* User logs into any of the application
* The application writes the session data into ElastiCache
* The user hits another instance of our application
* The instance retrieves the data and the user is already logged in

### II. Redis vs Memcached

#### REDIS
* Multi AZ with Auto-Failover
* Read replicas to scale reads and have high availability
* Data Durability using AOF presistence
* Backup and restore features
* Supports Sets and Sorted Sets

#### MEMCACHED
* Multi-node for partitioning of data (sharding)
* No high availability (replication)
* Non persistent 
* No backup and restore
* Multi-threaded architecture
