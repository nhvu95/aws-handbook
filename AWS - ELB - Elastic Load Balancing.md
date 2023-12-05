![image](https://github.com/nhvu95/aws-handbook/assets/26276890/8a587ff7-2040-47c1-a4b2-74ea5c1afa7e)
### What is load balancing?
* Load balances are servers that forward traffic to multiple servers (e.g. EC2 instances) downstream.

### Why use a load balancer?
* Spread load across multiple downstream instances
* Expose a single point of access DNS to your application.
* Seamlessly (Liền mạc) handle failure of downstream instances
* Do regular health checks to your instances
* Provide SSL termination (HTTPS) for your websites
* Enforce stickiness with cookies
* High availability across zones
* Separate public traffic from private traffic

### An Elastic Load Balancer is a managed load balancer
* AWS guarantees that it will be working
* AWS takes care of upgrades, maintenance, high availability
* AWS provides only a few configuration knobs (nút)

It costs less to setup your own load balancer, but it will be a lot more effort on your end.

#### It is integrated with many AWS offerings/services
* EC2, EC2 Auto scaling groups, Amazon ECS
* AWS Certificate Manager (ACM), CloudWatch
* Route 52, AWS WAF, AWS Global Accelerator

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/217213c7-1ae1-4602-be0e-2612d5326ffe)
### HealthCheck
- Health Checks are crucial for Load Balancers
- They enable the load balancer to know if the instances it forwards traffic to are available to reply to requests.
- The health check is done on a port and a route (/health is common)

### Types of load balancer on AWS
* AWS has 4 kinds of managed Load Balancers
* Clastic Load Balancer (V1 - old generation) - 2009 - CLB
  * HTTP, HTTPS, TCP, SSL (Secure TCP) - Deprecated and soon be removed
* Application Load Balancer (v2 - new generation) - 2016 - ALB
  * HTTP, HTTPS, WebSocket
* Network Load Balancer (v2 - new generation) - 2017 - NLB
  * TCP, TLS, UDP
* Gateway Load Balancer - 2020 - GWLB
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/97479bcf-3606-48c9-811c-00366814d950)

Overall, it is recommended to use the newer generation load balancers as they provide more features.
Some load balancers can be set as internal (private) or external (public) ELBs
