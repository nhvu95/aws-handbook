![image](https://github.com/nhvu95/aws-handbook/assets/26276890/fd205131-ed00-4b4c-a660-3cb5d7671dda)
* A Policies and apply for a group or a specific user
* A User can belong to multiple groups, it means that it can apply multiple policies at the same time

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/e41d46dd-f861-494d-a05e-be27148ccbea)
### IAM Policies Structure
* Policies version
* Id
* Statement (Statements consist of)
     * Sid: statement id (optional)
     * Effect: Whether the statement allows or denies access (Allow, Deny)
     * Principal: account/user/role to which this policy applied to
     * Action: list of actions this policy allows or denies
     * Resource: list of resources to which the actions applied to
     * Condition: conditions for when this policy is in effect (optional)


### IAM Policies Handon
* Inline policy created for a single IAM identity. They are deleted when the identity gets deleted.
* You can custom your policies by Visual Editor or JSON via AWS Console
