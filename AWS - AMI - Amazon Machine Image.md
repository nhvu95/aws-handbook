![image](https://github.com/nhvu95/aws-handbook/assets/26276890/63055640-26e7-483d-a204-f7024d68c108)

* AMI = Amazon Machine Image
* AMI are a customization of an EC2 instance
     * You add your own software, configuration, operating system, monitoriing
     * Faster boot / configuration time because all your software is pre-packaged
 * AMI are built for a specific region ( and can be copied across regions)
 * You can launch EC2 instances from
     * A public AMI: AWS provided
     * Your own AMI: You make and maintain them yourself
     * An AWS Marketplace AMI: an AMI someone else made ( and potentially sells )
 
* Start an EC2 instance and customize it
* Stop the instance for data integrity
* Build an AMI - this will also create EBS snapshots
* Launch instances from others AMIs

* Hand-on
