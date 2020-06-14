# Identity and Access Management

Reference:
* AWS Documentation: https://aws.amazon.com/iam/

IAM (for short), it's a global service, and it manages eveything related to users, groups and their level of access to the AWS Services, as well as the level of access between resources using AWS Services.

Permissions are handled by using *Policies* that are written in JSON, those policies can be attached to the different entities IAM manages:

* User
* Group
* Roles

There are different [types of policies][1]:


The features it offers are:

* Centralized control of your AWS account permissions
* It's Integrated with many (if not all) AWS services
* Offers granular permissions
* Has a set of Predefined "managed policies"
* Multi-Factor Authentication
* Identity Federation ([SAML], [Cognito])
* Provide temporary access for users/devices and services where necessary
* Set up password rotation policy
* Support PCI DSS compliance


## Security Best Practice
* **Never write, commit or share your IAM credentials**, store them securely
* **Don't ever use your root account**, create a new user as soon as you have logged in and configured all the suggested AWS security checks (MFA, etc)
* Give users the **least ammount of privileges** possible
* Create **ONE IAM user per Physical Person**
* Create **ONE IAM role per Application**
When you select policies for a user/group/role you can select specific policies or a jub function, which is a policy designed to closely align to a common job in the IT industry, ie: Database Administrator, Billing, Developer power-user, etc

New users has no permission when first created
You can only get to view user password and keys for only once. After that you will have to regenerate them

For a role you have to set the permissions but also the service/users that are allowed to assume this role

Power User Access allows access to all AWS services except the management of groups and users within IAM

[1]: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html