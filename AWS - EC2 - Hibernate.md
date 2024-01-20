### We know we can stop, and terminate instances

  * Stop - the data on disk (EBS) is kept intact in the next start
  * Terminate - any EBS volumes (root) also set-up to be destroyed is lost

### On start, the following happens:
  * First start: the OS boots & the EC2 User Data script is run
  * Following starts: the OS boots up
  * Then your application starts, caches get warmed up, and that can take time!

### Introducing EC2 Hibernate
  * The in-memory (RAM ) state is preserved
  * The instance boot is much faster ( The OS is not stopped / restarted)
  * Under the hood: the RAM state is written to a file in the root EBS volume
  * The root EBS must be encrypted

#### Use cases:
  * Long running processing
  * Saving the RAM state
  * Services that take time to initialize
  
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/5915f594-7bf9-4d86-bc67-189c6fd76d1f)
### EC2 Hibernate - Good to know
  * Supported instance families - C3, C4, C5...
  * Instance RAM Size - mustbe less than 150 GB
  * AMI - Amazon Linux 2, Linux AMI, Ubuntu, RHEL, CentOS & Windows
  * Root volume - Must be EBS, Encrypted, not instance store, and large
  * Available for On-Demand, Reserved, and Spot Instances

  * An instance can NOT be hibernated more than  60 days
