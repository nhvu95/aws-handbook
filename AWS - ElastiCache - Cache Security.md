![image](https://github.com/nhvu95/aws-handbook/assets/26276890/e753c080-edd8-4294-a59d-b0bfb3667058)

## AWS - ElastiCache - Cache Security
### AWS - ElastiCache - Cache Security

* ElastiCache supports IAM Authentication for Redis
* IAM policies on ElastiCache are only used for AWS API-level security
* Redis AUTH
    - You can set a "password/token" when you create a Redis cluster
    - This is an extra level of security for your cache (on top of security groups)
    - Support SSL in flight encryption
* Memcached
    - Suport SASL-based authentication (advanced)

#### I. Patterns for ElastiCache
* Lazy loading: all the read data is cached, data can become stale in cache
* Write Through: Adds or update data in the cache when written to a DB (No stale data)
* Session Store: store a temporary session data in a cache (using TTL features)

> Quote: There are only two hard things in Computer Science: cache invalidation and naming things

#### II. Redis Use Case
* Gaming Leaderboards are computationally complex
* Redis Sorted sets guarantee both uniqueness and element ordering
* Each time a new element added, it's ranked in real time, then added in correct order
