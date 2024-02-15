![image](https://github.com/nhvu95/aws-handbook/assets/26276890/134958a7-a883-46f3-ba46-7287c99a938a)

## AWS - Route 53
### 1. Routing policies

The Route 53 policies are intended to manage and control routing in the domain layer, which means it was born to support higher levels in multiple regions. This is different from the ELB, which supports a single region and controls and balances between resources (EC2) in a region.

### 2. CNAME vs Alias:
  * CNAME allowed you to point a hostname to any other hostname ( app.mydomain.com => blabla.anydomain.com ). Only work for non-root domain name.
  * Alias: Point your host name to AWS resource. Free of charge

### 3. Routing policies - Simple:
  * Routing traffic to single resource. Can specify multiple values in the same record.
  * If multiple value are returned, the random one is chossen by the client
  * When Alias is enabled, specify only one AWS resource
  * Can be associate with Health check
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/b9e29ee5-2dc4-464c-b386-d7518c91a84b)

### 4. Routing policies - Weighted: ( Trọng số)
  * Control the % of requests that go to each specific resource
  * % = weight / sum of all the weights
  * DNS records must have the same name and type
  * Can be associate with HealthChecks
  * Load balancing between region, testing new application versions.
  * Set a weight 0 to a record to stop sending traffic to a resource
  * If all records are 0, they will be the same rate
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/7d83c27c-89c8-4f20-86b2-cf9328380b76)

### 5. Routing policies - Latency
  * Redirect ot the resource that has the least latency close to us
  * Super helpful when latency for users is a priority
  * Latency is based on traffic between users and AWS Regions
  * Can be associated with Health checks (Has failover capacity)

### 6. Routing policies - Health-checks
   ![image](https://github.com/nhvu95/aws-handbook/assets/26276890/ef43072c-c5fd-41d3-93db-c1215dd46e3d)
   * HTTP Health check are only for public resources
   * Health Checks => Automated DNS Failover
   * About 15 global health-checkers will check the endpoint health
      * Healthy/Unhealthy Threshold - 3 (default)
      * Interval - 30 sec (can set to 10 sec - higher cost)
      * Supported protocol: HTTP, HTTPS and TCP
      * If > 18% of health checkers report the endpoint is healthy, Route 53 considers it healthy, otherwise it's unhealthy.
      * Ability to choose which locations you want Route 53 to use
   * Health Checks pass only when the endpoint responds with the 2xx or 3xx status codes
   * Health Checks can be setup to pass/fail based on the text i nthe first 5120 bytes of the response
   * Configure you router/firewall to allow incoming request form Route 53 Health Checkers

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/7f4a2295-00a2-4084-aa07-66c7ef89bbb4)
#### 6.1 Calculate health check
   * Combine the results of multiple Health Checks into a single Health Check
   * You can use OR, AND, NOT
   * Can monitor up to 256 Child Health Checks
   * Specify how many of the health checks need to pass to make the parent pass
   * Usage: Perform maintenance to your website without causing all health check to fail
#### 6.2 Health check on privated zones
   * Route 53 heath checkers are outside the VPC
   * They can't access private endpoints (private VPC or on-premise resource)
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/98a968d5-dba2-473f-9ecd-9f3c657b31a5)
Solution: You can create a Cloud Watch Metric, and associate a CloudWatch Alarm, then create a HealthCheck that checks the alarm itself

### 7. Routing policies - Failover
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/38b736e6-e577-4784-b795-49da153496f4)

### 8. Routing policies - Geolocation
* Different from latency-based
* This routing is based on user location
* Specify location by Continent, Country or by US State (if there's overlapping, most precise location selected)
* Should create a "Default" record (in case there's no match on location)
* Use cases: website localization, restrict content distribution, load balancings...
* Can be associated with Health Checks

### 9. Routing policies - Geoproximity
* Route traffic to your resources based on the geographic location of users and resources
* Ability fo shift more traffic to resources based on the defined bias
* To change the side of the geographic region, specify bias value
   * To expand (1-99) more traffic to the resource
   * To shrink (1-99) less traffic to the resource
* Resources can be:
   * AWS resources (specify AWS region)
   * Non-AWS resources (specify Latitude Longitude)
* You must use Route 53 Traffic Flow (advanced) to use this feature
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/be9b4d2b-3a7a-4132-a019-debd1736cbf8)

### 10. Routing policies - IP-based Routing
* Routing is based on clients's IP addresses
* You provide a list of CIDRs for your client (CIDRs for example 40.102.53.xx) and the corresponding endpoints/locations (user-IP-to-endpoint mappings)
* Use cases: Optimize performance reduce network costs...
* Example: route end users form a particular ISP to a specific endpoint

![image](https://raw.githubusercontent.com/nhvu95/aws-handbook/main/AWS%20-%20Route%2053-1708003953709.png)