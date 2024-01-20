* On-Demain instances - short workload, predictable pricing, pay by second
* Reserved (1 & 3 years)
   * Reserved instances - long workload
   * Convertible reserved instances - long workloads with flexible instances
* Saving plans ( 1 & 3 years) - Commitment to an amount of usage, long workload
* Spot instances - short workloads, cheap, can lose instances
* Dedicated host - book entire physical server, control instance placement
* Dedicated instances - no other customer will share your hardware
* Capacity Reservations - reserve capacity in a specific AZ for any duration


### I. On-demand
* Pay for what you use: 
   * Linux or Windows - billing per second, after the first minute
   * All other operating systems - billing per hour
* Has the highest cost but no upfront payment
* No long-term commitment

* Recommended for short-term and un-interrupted workloads, where you can't predict how the application will behave

### II. Reserved instances
* Up to 72% discount compared to On-demand
* You reserve specific instance attributes ( Instance Type, Region, Tenancy, OsS)
* Reservation period - 1 year ( + discount) or 3 year (+++ discount)
* Payment options - No upfront (+), Partial Upfront (++), All Upfront (+++)
* Reserved instance's scope - regional or Zonal ( reserve capacity in an AZ)
* Recommended for steady-state usage applications (think database)
* You can buy and sell in the reserved instance marketplace
* Convertible Reserved Instance
    * Cna change the EC2 instance type, instance family, OS, scope and tenancy
    * Up to 66% discount

### III. Saving plans
* Get a discount based on long-term usage ( Up to 72% same as RIs)
* Commit to a certain type of usage ( $10/hour for 1-3years)
* Usage beyond EC2 Saving plans is billed at the On-Demand price
* Locked to a specific instance family & AWS region (eg. M5 in us-east-1)
* Flexible across:  Instance size (e.g. m5.xlarge, m5.2xlarge), OS (e.g. Linux, Windows), Tenancy (Host, Dedicated, Default)

### IV. EC2 Spot Instances
* Discount up to 90% compared to On-Demand
* Instances that you can lose at any point in time if your max price is less than the current spot price
* The MOST cost-efficient instances in AWS

* Useful for workloads that are resilient to failure
    * Batch jobs,
    * Data analysis
    * Image processing
    * Any distributed workloads
    * Workloads with a flexible start and end time

* Not suitable for critical jobs or databases

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/18332de9-5b7e-4eca-b371-7f24aea9bc94)

### V. Dedicated Host
* A physical server with EC2 Instance capacity fully dedicated to your use
* Allows you to address compliance requirements and use your existing server-bound software licenses (per-socket, per-core, per-VM software licenses)
* Purchasing Options:
    * On-demand - pay per second for active Dedicated Host
    * Reserved - 1 or 3 years (No Upfront, Partial Upfront, All Upfront)
* The most expensive option

* Useful for software that has a complicated licensing model ( BYOL - Bring your own license)

### VI. Dedicated Instances
* Instances run on hardware that's dedicated to you
* May share hardware with other instances in the same account
* No control over instance placement ( Can move hardware after Stop/Start)

### VII. Capacity Reservations
* Reserve On-Demand instances capacity in a specific AZ for any duration
* You always have access to EC2 capacity when you need it
* No time commitment ( Create/cancel anytime), No billing discount)
* Combine with Regional Reserved instances and Savings Plans to benefit from billing discounts
* You're charged at an On-Demand rate whether you run instances or not
* Suitable for short-term, uninterrupted workloads that need to be in a specific AZ

Upfront: trả trước
