![image](https://github.com/nhvu95/aws-handbook/assets/26276890/95fefff4-6b2f-4aaf-b773-17920277cc15)

* Users have access to your account and can change configurations or delete resources in your AWS account
* You want to protect your Root Accounts and IAM users
* MFA = password you know + MFA + security device you own
* (Multiple factor authentication)
* Virtual MFA devices: Google Authenticator, Authy
* U2F = A hardware key Yubikey, like encrypted USB
* MFA = Hardware key, a small device that generates a key and then displays it on the screen in real-time.

### Hand-on
From IAM > Account Setting > Edit password policy
From IAM > Security Credentials > Assign MFA devices
