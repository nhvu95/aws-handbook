## AWS - Route 53
### Routing policies

- CNAME vs Alias:
  - CNAME allowed you to point a hostname to any other hostname ( app.mydomain.com => blabla.anydomain.com ). Only work for non-root domain name.
  - Alias: Point your host name to AWS resource. Free of charge

- Simple:
  - Routing traffic to single resource. Can specify multiple values in the same record.
  - If multiple value are returned, the random one is chossen by the client
  - When Alias is enabled, specify only one AWS resource
  - Can be associate with Health check

- Weighted: ( Trọng số)
  - Control the % of requests that go to each specific resource
  - % = weight / sum of all the weights
  - DNS records must have the same name and type
  - Can be associate with HealthChecks
  - Load balancing between region, testing new application versions.
  - Set a weight 0 to a record to stop sending traffic to a resource
  - If all records are 0, they will be the same rate


