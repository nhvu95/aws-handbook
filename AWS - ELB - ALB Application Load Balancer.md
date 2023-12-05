![image](https://github.com/nhvu95/aws-handbook/assets/26276890/92cee5cf-322b-4c42-8fa6-e67577642d94)

- Application Load Balancer is Layer 7 (HTTP)

- Load balancing to multiple HTTP applications across machines (target groups)
- Load balancing to multiple applications on the same machine (ex: containers)
- Support for HTTP/2 and WebSocket
- Support redirects ( from HTTP to HTTPS for example)
- Support group routings, routing tables to different target groups:
    - Routing based on the path in URL ( example.com/user & example.com/post )
    - Routing based on hostname in URL (one.example.com & other.example.com )
    - Routing based on Query String, Headers ( example.com/users?id=123&order=false)

- ALB are a great fit for microservices and container-based application (example: Docker & Amazon ECS)
- Has a port mapping feature to redirect to a dynamic port in ECS
- In comparison, we'd need multiple Classic Load Balancer per application
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/55518c55-7607-4f6b-9cee-de58e1ca6e04)

### Application Load Balancer (v2) Target Groups
- EC2 instances (can be managed by an Auto Scaling Group) - HTTP
- ECS Tasks ( managed by ECS itself) - HTTP
- Lambda functions - HTTP request is translated into a JSON event
- IP Addresses - Must be private IPs

- ALB can route to multiple target groups
- Health checks are at the target group level

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/79f14aa0-b81a-4b79-8518-8ca5a801199e)
### Good to know
* Fixed hostname XXX.region.elb.amazonaws.com
* The application servers don't see the IP of the client directly
   - The true IP of the client is inserted in the header X-forwarded-For
   - We can also get Port ( X-Forward-Port) and proto (X-Forwarded-Proto)
