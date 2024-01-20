![image](https://github.com/nhvu95/aws-handbook/assets/26276890/77ac80e4-fcc7-459b-b0f3-cdeb28f45466)
### Revise
Networking has two sorts of IPs, IPv4 and IPv6
IPv4: 1.160.10.240
IPv6: 3ffe:1900:4545:3:200:f8ff:fe21:67cf

IPv4 is still the most common format used only
IPv6 is newer and solves problems for the Internet of Thing (IOT)

IPv4 allows for 3.7 billion different addresses in the public space
IPv4: [0-255].[0-255].[0-255].[0-255]

### Public IP
   * Public IP means the machine can be identified on the internet (WWW_
   * Must be unique across the whole web (not two machines can have the same public IP)
   * Can be geo-located easily

### Private IP:
   * Private IP means the machine can only be identified on a private network only
   * The IP must be unique across the private network
   * BUT two different private networks (two companies) can have the same IPs.
   * Machines connect to WWW using an internet gateway (a proxy)
   * Only a specified range of IPs can be used as private IP

### Elastic IP
   * When you stop and then start an EC2 instance, it can change its public IP
   * If you need to have a fixed public IP for your instance, you need an Elastic IP
   * An Elastic IP is a public IPv4 IP you own as long as you don't delete it.
   * You can attach it to one íntance at a time
   * With an Elastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account.
   * You can only have 5 Elastic IP in your account (You can ask AWS to increase that)
   * Overall, try to avoid using Elastic IP. Instead, use a random public IP and register a DNS name to it. Or, as we'll see later, use a Load Balancer and don't use a public IP
   * You can access Elastic IP via the EC2 menu on the left, then Associate an Elastic IP to an instance or to a Network 
