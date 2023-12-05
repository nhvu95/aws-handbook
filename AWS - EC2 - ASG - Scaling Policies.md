![image](https://github.com/nhvu95/aws-handbook/assets/26276890/a6a23990-9c8a-4594-a98b-89a4c56c5fac)

## ASG - Dynamic Scaling Policies
  * Target Tracking Scaling
   - Most simple and easy to setup
   - Example: I want the  average ASG CPU to stay around 40%

  * Simple / Step scaling
   - When a CloudWatch alarm is triggered (for example CPU > 70%), then add 2 units
   - When a CloudWatch alarm is triggered (for example CPU < 30%) then remove 1

  * Scheduled actions
    - Anticipate a scaling based on know usage patterns
    - Example: increase the min capacity to 10 at 5pm on Fridays

### ASG - Predictive Scaling
* Predictive scaling: continuously forecast load and schedule scaling ahead

### Good metrics to scale on
* CPU Utilization: Average CPU utilization across your instances
* RequestCountPerTarget: To make sure the number of requests per EC2 instances is stable
* Average Network In/Out (if you're application is network bound)
* Any custom metric (that you push into CloudWatch)

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/836efb9a-b3ce-43ed-8847-6495d60a70fe)

### Auto Scaling Groups - Scaling Cooldowns
* After a scaling activity happens, you are in the cooldown period (default 300 seconds)
* During the cooldown period, the ASG will not launch or terminate additional instances ( to allow for metrics to stabilize)

> Advice: Use a ready-to-use AMI to reduce configuration time in order to serve requests faster and reduce the cooldown period

