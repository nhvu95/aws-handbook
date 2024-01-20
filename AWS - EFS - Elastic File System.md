![image](https://github.com/nhvu95/aws-handbook/assets/26276890/d32d8007-a7bc-4545-b56e-caa8add9268d)

• Manage NFS (Network file system) that can be mounted on many EC2
• EFS works with EC2 instances in multi-AZ
• Highly available, scalable, expensive (3x gp2), pay per use

• Use case: content management, web serving, data sharing, WordPress
• Uses NFSv4,1 protocol
• Use the Security Group to control access to EFS
• Compatible with Linux-based AIMI (not Windows)
• Encryption at rest using KMS

- POSIX file system (~Linux) that has a standard file API
- File system scales automatically, pay-per-use, no capacity planning!

## I. Performance & Storage Classes
### I.I EFS scale
      - 1000s of concurrent NFS clients, 10GB+ /s throughput
      - Grow to Petabyte-scale network file system, automatically
### I.II Performance Mode (set at EFS creation time)

      - General Purpose (Default) - latency-sensitive use cases (web server, CMS etc.)
      - Max I/O - higher latency, throughput, highly parallel ( big data, media processing)
### I.III Throughput Mode

      - Bursting - 1TB = 50MiB/s + burst of up to 100MiB/s
      - Provisioned - set your throughput regardless of storage size, ex: 1GB/s for 1TB storage
      - Elastic - automatically scales throughput up or down based on your workload
              + Up to 3GIB/s for reads and 1 GiB/s for writes
              + Used for unpredictable workloads

### I.IV Storage Tiers (lifecycle management feature - move file after N days)
         - Standard: for frequently accessed files
         - Infrequent access (EFS-IA) cost to retrieve files, lower price to store, Enable EFS-IA with a Lifecycle Policy

         - Availability and durability
         - Standard: Multi-AZ, great for prod
         - One Zone: One AZ, great for dev, backup enabled by default, compatible with IA (EFS One Zone-IA)
         - Over 90% in cost savings

