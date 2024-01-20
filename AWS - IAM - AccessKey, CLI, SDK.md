* To access AWS, you have three options:
* AWS Management Console ( Via web browser)
* AWS Command Line Interface (CLI): Protected by access keys
* AWS Software Developer Kit (SDK): For code - protected by access keys

* Access keys are generated through the AWS Console
* Users manage their own access keys
* Access keys are secret, just like passwords. Don't share them.
* Access Key ID ~= username
* Secret Access Key ~= Password

CLI: is a tool that enables you to interact with AWS services using commands in your command-line shell
* Direct access to the public APIs of AWS services
* You can develop scripts to manage your resources
* It's open*source AWS-CLI
* Alternative to using AWS Management Console

SDK: Software Development Kit (AWS SDK)
* A language-specific APIs (set of libraries)
* Enables you to access and manage AWS services programmatically
* Embedded within your application
* Supports a lot of programming languages

AWS CLI is built on AWS SDK for Python

Hand-on:
IAM > Select A User > Security Credentials > Scroll down and select Create Access Key
`aws configure`, then enter the Access key - information 
