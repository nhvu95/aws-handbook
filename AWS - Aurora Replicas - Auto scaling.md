## Aurora Replicas - Autoscaling
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/74cdf1ee-c313-48e4-8540-9a81e871d0e5)
* Autoscaling the replicas
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/cea6185b-adf2-44cb-9cce-e14a9a0b3cac)
* Custom endpoints
  - Defined a subset of Aurora Instance as a Custom Endpoint
  - Example: Run analytical queries on specific replicas
  - The Reader Endpoint is generally not used after defining Custom Endpoints

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/7df272af-d596-40d6-a6aa-a003bee2fd99)

### I. Aurora Serverless
* Automated database instantiation and auto-scaling based on actual usage
* Good for infrequent, intermittent or unpredictable workloads
* No capacity planning needed
* Pay per second, can be more cost-effective
  
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/00d288ab-c601-4426-8795-a52227e1fe8b)
### II. Aurora Multi-Master
* In case you want continuous write availability for the writer nodes
* Every node does R/W - vs promoting a Read replica as the new master

### III. Global Aurora
* Aurora Cross Region Read Replicas
 - Useful for disaster recovery
 - Simple to put in place
* Aurora Global Database (recommended):
 - I primary region (read/write)
 - Up to 5 secondary (read/only) regions, replication lag is less than 1 second
 - Up to 16 Read replicas per secondary region
 - Helps for decreasing latency
 - Promoting another region (for disaster recovery) has an RTO of < 1 minute
 - Typical cross-region replication takes less than 1 second

### IV. Aurora Machine Learning
* Enables you to add ML-based predictions to your applications via SQL
* Simple, optimized, and secure integration between Aurora and AWS ML services
* Supported services
      - Amazon SageMaker (use with any ML model)
      - Amazon Comprehend (for sentiment analysis)
* You don't need to have ML experience
* Use cases: fraud detection, ads targeting, sentiment analysis, product recommendations
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/f45fba79-15a8-48c3-8cf7-b9bf0004d997)
