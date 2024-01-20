* IAM Credentials report (account*level)
a report that lists all your account's users and the status of their various credentials

* IAM Access Advisor (user*level)
Access Advisor shows the service permissions granted to a user and when those services were last accessed
* You can use this information to revise your policies

Hand*on
* Download the credential report in the sidebar of IAM
* View Access Advisor in IAM > Users > Select user

IAM Best practices
* Don't use the root account, except for the AWS account setup
* One physical user = One AWS user
* Create a strong password policy, MFA 
* Assign users to a group and assign permission to groups
* Create Roles and assign permission to AWS services
* Use Access keys for Programmatic Access (CLI /SDK)
* Audit permission of you account using IAM Credentials Report & IAM Access Advisor
* Never share IAM user & Access Keys
