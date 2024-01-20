![image](https://github.com/nhvu95/aws-handbook/assets/26276890/32117ccf-2147-406f-838f-cd4033724339)

* Security groups are fundamental to network security in AWS
* They control how traffic is allowed into or out of our EC2 Instances
* A Security groups only contain allowed rules,
* Security groups rules can reference by IP or security group

* Security groups are acting as a firewall on EC2 instances
* They regulate: 
   * Access to Ports
   * Authorised IP ranges * IPv4 and IPv6
   * Control of inbound network ( from other to the instance)
   * Control of outbound network ( from instances to other)

* Good to know
   * A Security group can be attached to multiple instances.
   * An instance only can be attached to one security group,
   * Locked down to a region  / VPC combination
   * A SGroup live outside of the EC2 * if traffic is blocked the EC2 instance won't see it
   * It is good to maintain one separate security group for SSH access
   * If your application is not accessible (time out), then it's a security group issue
   * If your application gives a "connection refuse" error, then it's an application error, or it has not launched
   * All inbound traffic is blocked by default
   * All outbound traffic is authorised by default

Some ports: 22, 21, 3489, 80, 443

• EC2 Hand ons
