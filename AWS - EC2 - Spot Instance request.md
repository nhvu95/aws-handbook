![image](https://github.com/nhvu95/aws-handbook/assets/26276890/7be977d8-90d6-48b8-9a92-a7dc1cdbe203)

* Can get a discount of up to 90% compared to On-demand
* Define max spot price and get the instance during the current spot price < max
    * The hourly price varies based on offer and capacity
    * If the current spot price > your max price, you can choose to stop or terminate your instance with a 2 minutes grace period

* Other strategy: Spot block
    * "Block" spot instances during a specified time frame ( 1 to 6 hours ) without interruptions.
    * In rare situations, the instance may be reclaimed

* Used for batch jobs, data analysis, or workloads that  are resilient to failures
* Not great for critical jobs or database

### I. How to terminate spot instances
You must first cancel a Spot Request and then terminate the associated Spot Instance.

### II. Spot Fleets
* Spot Fleets =  set of Spot Instances + (optional) On-Demand Instances
* The Spot Fleet will try to meet the target capacity with price constraints
    * Define possible launch pools: instance type (m5.large, OK, Availability Zone
    * Can have multiple launch pools so that the fleet can choose
    * Spot Fleet stops launching instances when reaching capacity for max cost
* Strategies to allocate Spot Instances:
    * lowestPrice: from the pool with the lowest price ( cost optimization, short workload)
    * diversified: distributed across all pools ( greater for availability, long workloads)
    * capacityOptimized: pool with the optimal capacity for the number of instances
    * priceCapacityOptimized (recommended): pools with the highest capacity available, then select the pool with the lowest price ( best choice for the most workload)

* Spot Fleets allow us to automatically request Spot Instances with the lowest price
