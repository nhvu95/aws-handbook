sophisticated: (adj) cầu kì  
diverse: (adj) phong phú  
discrete: (adj) rời rạc  
isolated (adj) cô lập  
disaster: thảm họa  
presence: sự hiện diện  

### AWS Regions:
* AWS has regions all around the world
* Names can be us-east-1, eu-west-3
* A region is a cluster of data centers
* Most AWS services are region-scoped
* Choose a Region based on Compliance, Proximity - latency, Available services ( some regions unavailable some services - you can check them on the website), Pricing

### Available Zones:
* Each region has many availability zones, usually 3, min is 3, max is 6.
* For example: Sydney `ap-southeast-2` have three available zones ap-southeast-2a, ap-southeast-2b, ap-southeast-2c
* Each AZ is one or more discrete data centers with redundant power, networking, and connectivity
* AZs are separate from each other, so they are isolated from disaster
* AZs are connected with high bandwidth, ultra-low latency networking

### Edge locations:
* Amazon has 400+ Edge locations & 10 Regional Caches in 90+ cities & 40+ countries
* Content is delivered to end users with lower latency

### Some global services:
* IAM (Identity and Access Management)
* Route 53 (DNS Service)
* CloudFront (CDN)
* WAF (Web application firewall)

### Most AWS services are Region-scoped
* EC2 (Infrastructure as a service)
* Elastic Beanstalk (Platform as a service)
* Lambda (Function as a service)
* Rekognition (Software as a service)
