![image](https://github.com/nhvu95/aws-handbook/assets/26276890/86c0e6d2-de85-4d85-939b-fd706a20119a)

## ASG - Auto Scaling Group
* In real life, the load on your websites and applications can change
* In the cloud, you can create and get rid of servers very quickly

* The goal of an auto Scaling Group (ASG) is to:
  * Scale-out (add EC2 instances) to match an increased load
  * Scale-in (remove EC2 instances to match a decreased load)
  * Ensure we have a minimum and a maximum number of EC2 instances running
  * Automatically register a new instance to a load balancer
  * Re-create an EC2 instance in case a previous one is terminated (ex: unhealthy)

* ASG are free ( you only pay for the underlying EC2 instances)

### AUTO SCALING GROUP ATTRIBUTES
* A Launch Template (older "Launch Configurations" are deprecated)
  * AMI + Instance type
  * EC2 User Data
  * EBS Volumes
  * Security Groups
  * SSH Key Pair
  * IAM Roles for your EC2 Instances
  * Network + Subnets Information
  * Load Balancer Information
* Min Size / Max Size / Initial Capacity
* Scaling Policies
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/f05074e7-4852-44c2-8b75-669430378355)
* It is possible to scale and ASG based on Cloud Watch alarms
* An alarm monitors a metric (such as an Average CPU or a custom metric)
* Metrics such as Average CPU are computed for the overall ASG instances
* Based on the alarm
  - We can create scale-out policies ( increase the number of instances)
  - We can create scale-in policies
