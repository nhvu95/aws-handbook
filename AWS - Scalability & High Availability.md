![image](https://github.com/nhvu95/aws-handbook/assets/26276890/465b165d-5605-42c3-bd5f-a730bc6fe549)

### I. Scalability
- Scalability means that an application/system can handle greater loads by adapting.
- There are two kinds of scalability
     + Vertical Scalability
     + Horizontal Scalability (= elasticity)
- Scalability is linked but different to High Availability

- Let's deep dive into the distinction, using a call centre as an example

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/502d6d3f-2c06-43ca-a548-e926f4a38567)
#### Vertical Scalability
- Vertically scalability means increasing the size of the instance
     Ex: increase a junior operator to a senior operator
- For example, your application runs on a t2.micro
- Scaling that application vertically means running it on a t2.large
- Vertical scalability is very common for non-distributed systems, such as a database.
- RDS, and ElastiCache are services that can scale vertically
- There's usually a limit to how much you can vertically scale (hardware limit)
- 
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/eb5cdb77-c9fb-4a74-96b8-d4fd6a54e070)
#### Horizontal Scalability
- Horizontal scalability means increasing the number of instances/systems for your application.
- Horizontal scaling implies distributed systems.
- This is very common for web applications /  modern applications
- It's easy to horizontally scale thanks the cloud offerings such as Amazon EC2

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/b413785a-fbc5-4b60-9dd3-bd0d4843ac32)
### II. High Availability
- High Availability usually goes hand in hand with horizontal scaling.
- High Availability means running your application/system in at least 2 data centres (== AZ)
- The goal of High Availability is to survive a data centre loss
- High Availability can be passive (for RDS Multi-AZ for example)
- High Availability can be active (for horizontal scaling)

### III. High Availability & Scalability For EC2
 - Vertical scaling: Increase instance size (scale up/down)
 - Horizontal scaling: increase the number of instances (= scale out / in)
     * Auto-scaling group
     * Load balancer
- High Availability: Run instances for the same application across multi-AZ
     * Autoscaling Group multi-AZ
     * Load balancer multi-AZ
