privilege: (n) đặc quyền
principle: (n) nguyên tắc

- IAM = Identify and Access Management, Global service. Whatever you are, you always have the same users.
- Root account created by default, which shouldn't be used or shared
- Users are people within your organization and can be grouped
- Groups only contain users, not other groups
- Users don't have to belong to a group; a user can belong to multiple groups.

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/0742c0fd-6dff-46af-9e64-c1bfe763b4c1)
### IAM: Permission
- Users or Groups can be assigned JSON documents called policies
- These policies define the permissions of the users
- The least privilege principle: Don't give more permission than a user needs.

### IAM: Create a user
- Besides basic information, you can config a user based on a specified user in IC - Identity Center or create an IAM user.
- When creating a user, you can add this user to a group or add policies directly.
- And add a tag for this user, which has more meaning and use later can use everywhere
- After creating successfully, you can download the .csv file, which contains user_name and password, or back to the user's list
- Account alias is an alias to easy login instead of AccountID

![image](https://github.com/nhvu95/aws-handbook/assets/26276890/9a223aa8-8096-4f23-b49a-5ed77b2b580f)
### IAM: Create a group
- When creating a group, you can select some built-in policies
- You can manage users in this group
- You can manage policies applied for this group

### IAM: Best practice
- Avoid using the Root account. Create an Admin account from the root account and use it instead.
