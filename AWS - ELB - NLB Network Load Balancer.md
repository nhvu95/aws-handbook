![image](https://github.com/nhvu95/aws-handbook/assets/26276890/b2357b72-0d9a-4083-b544-787b047cd6c9)

- Network load balancer (Layer 4) allows to:
    - Forward UDP and TCP traffic to your instances
    - Handle millions of requests per second
    - Less latency ~100ms (vs ~400ms of ALB)

- NLB has one static IP per AZ and supports assigning Elastic IP (helpful for whitelisting specific IP)
- NLB is used for extreme performance, TCP or UDP traffic
- Not included in the Free tier

- Target group which NLB supported
    - EC2 Instances
    - IP Addresses - must be Private IPs
    - Application Load Balancer
- Health check support TPC, HTTP, HTTPS Protocols
