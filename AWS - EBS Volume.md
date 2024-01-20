
* An EBS (Elastic Block Store) Volume is a network drive you can attach to your instances while they run.
* It  allows your instances to persist data, even after their termination
* They can only be mounted to one instance at a time ( at the CCP level). CCP - Certified Cloud Practitioner - One EBS can be only mounted to one EC2 instance Associate Level (Solutions Architect, Developer, SysOps): '"multi-attach" feature for some EBS
* They are bound to a specific availability zone.

* Analogy: Think of them as a "network USB stick"
* Free tier: 30GB of free EBS storage of type General Purpose (SSD) or Magnetic per month.
* It's  a network drive (i.e not a physical drive)
      - It uses the network to communicate the instance, which means there might be a bit of latency
      - It can be detached from an EC2 instance and attached to another one quickly.
  
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/941f177e-22c8-4db7-b9f9-bb1e21def67c)
* It's locked to an Availability Zone (AZ)
    - An EBS Volume is us-east-Ia cannot attach to us-east-Ib
    - To move a volume across, you first need to snapshot it

* Have a provisioned capacity (size in GBs, and IOPS)
   - You get billed for all the provisioned capacity
   - You can increase the capacity of the driver over time
 
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/8fc3b536-d5d2-4379-bd1e-52e45432edb6)

* Delete on termination attribute
When we create an EBS, there is an option by default that will be ticked for Root volume but not ticked for EBS volume.
 * By default, the root EBS volume is deleted ( attribute enabled)
 * By default, any other attached EBS volume is not deleted ( attribute disabled)
 * Use case: preserve root volume when an instance is terminated
