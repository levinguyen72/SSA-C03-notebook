## IAM (Identity & Access management)

# Users and Groups
- **Root account** create by default, shouldn't be used or shared
- **Users** are people in organization, can be grouped, can belong to multi-group
- **Groups** only contain user, cannot contain group

# IAM Role
- **Roles** is identity has specific permission using for short duration

# IAM permission
- **Users or Groups** can be assigned JSON documnents called policies, these policies define permissions of the users
- In AWS should apply the **least privilege principle** don't give more than user need

# IAM policies structure
* Consists of 
**Version**: policy language version, always include "2023-12-21"
**Id**: an identifier for the policy(optional)
**Statement**: one or more individual statements
- **Statement consists of**
**Sid**: and identifier for the statement
**Effect**: Allow or Deny
**Principle**: account/user/role to which this policy applied to 
**Action**: list of actions th is policy allows or denies
**Resource**: list of resources to whichs the actions applied to 
**Condition**: conditions for when this pilicy is in effect (optional)

# Multi factor authentication (MFA)

# Access AWS
1 AWS management console ( protected by password and MFA)
2 AWS command line interface (CLI protected by access keys)
3 AWS software developer kit (SDK - for code, protected by access keys)
- Users manage their own access key
- Access key are secret, Access key ID ~= username, secret access key ~= password

# CloudShell
# AWS Orginization

# IAM Credentials (Account level)
- List all account'users and the status of their various credentials
# IAM Access Advisor (User level)
- Access advisor shows the service permission granted to users and when those sevices were last accessed

# Best practice
- Don't use the root account excepting for AWS account set up
- One physical user = One AWS user
- Assign users to groups and assign permission to groups
- Create a strong password policy
- Use and enforce the use of MFA
- Create and use Roles for giving permission to AWS services
- Using Access keys for programmatic Access (CLI, SDK)
- Never share IAM users & Access keys
# Summary 
- Users: mapped to a physical user, has a password
- Groups: contains users only
- Policies: JSON document that outlines permission for users or groups
- Roles: for EC2 instances for AWS services
- security: MFA + Password policy
- Access keys: access AWS using the CLI or SDK
- Audit: IAM Credential Reports & IAM Access advisor