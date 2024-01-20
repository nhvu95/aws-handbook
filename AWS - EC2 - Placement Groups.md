* Sometimes, you want control over the EC2 Instance placement strategy
* That strategy can be defined using placement groups
* When you create a placement group, you specify one of the following strategies for the group:
   * Cluster - Clusters instances into a low-latency group in a single availability zone,
   * Spead - Speads instances across underlying hardware (max 7 instances per group per AZ) - critical applications
   * Partition - spreads instances across many different partitions ( Which rely on different sets of racks) within AZ, Scales to 100s of EC2 instances per group ( Hadoop, Cassandra, Kafla)

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/57cd385b-82d8-4622-8ae8-091211cf25b1)
### Cluster
   * All of these EC2 instances are in the same Rack, the same  hardware, and the Same AZ
   * Pros: Great network ( 10Gbs bandwidth between instances).
   * Cons: If the rack fails, all instances fails at the same time
   * Use case: 
        * Big data jobs that need to complete fast
        * Applications that need extremely low latency and high network throughput

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/2f78fc6e-98fb-4220-b8dc-2eece4158edc)
### Spread
   * All of the EC2 instances are in the different hardware
   * Pros: Can span across AZ
       * Reduced risk is a simultaneous failure
       * EC2 Instances are on different physical hardware
   * Cons
       * Limited to 7 instances per AZ per placement group
   * Use case:
       * Application that needs to maximize high availability
       * Critical Applications where each instance must be isolated from failure from each other.

### Partition
   * In multiple AZs
   * Each partition represents for a rack in AWS
   * Up to 7 partitions per AZ
   * Can span across multiple AZs in the same region
   * Up to 100s of EC2 instances
   * The instances in a partition do not share racks with the instances in the other partitions
   * Each partition is isolated from failure
   * EC2 instances get access to the partition information as metadata
   * Use case: HFDFs, HBase, Cassandra, Kafla
