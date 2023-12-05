![image](https://github.com/nhvu95/aws-handbook/assets/26276890/62e56b3d-9c21-4da0-bd70-a2fe80081c98)

* Feature naming
      * Connection Draining - for CLB
      * Deregistration Delay - for ALB & NLB

* Time to complete in-flight requests while the instance is de-registering or unhealthy
* Stops sending new requests to the EC2 instance, which is de-registering
* Between 1 to 3600 seconds (default: 300 seconds)
* Can be disabled ( set value to 0)
* Set to a low value if your requests are short
