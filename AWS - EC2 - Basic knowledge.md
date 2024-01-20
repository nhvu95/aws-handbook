### Overview
* EC2 is one of the most popular of AWS's offering
* EC2 = Elastic Compute Cloud = Infrastructure as a Service
* It mainly consists of the capability of:
     * Renting virtual machines (EC2)
     * Storing data on virtual drives (EBS)
     * Distributing load across machines (ELB)
     * Scaling the services using an auto*scaling group
* Knowing EC2 is fundamental to understanding how the Cloud works.

### EC2 sizing & Configuration options
* AWS Allows us to choose Operating System (OS): Linux, Windows or MacOS
* How much compute power & cores (CPU)
* RAM
* Storage space: Network*attached EBS & EFS, Hardware
* Network card: Speed of the card, Public Ip address
* Firewall rules, security group
* Bootstrap script

### EC2 Bootstrapping
* Bootstrapping means launching commands when a machine starts. It calls EC2 User data script.
* That script is only run once at the instance's first start.
* EC2 user data is used to automate boot tasks such as
    * Installing updates
    * Installing software
    * Downloading common files from the internet
    * Anything you can think of
* EC2 User Data script runs with the root user.
* There are many EC2 instance types

### Hands*On
* A Key pair allows you to connect to your instance securely, SSH, RDP
* Security Group (Firewall) where you configure inbound and outbound
* Allow SSH traffic from the internet > config specific IP filter
* Delete on termination, => delete volume when EC2 terminated
* Paste a bash script into the User data part to configure bootstrapping script.
