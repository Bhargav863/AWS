* AWS IAM (Identity and Access Management) is a webservice that helps you to securely control the access to the entire AWS resources centrally.
* IAM is used for security Purposes.
* You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.
* IAM is completely Free and it is a Global service
* key components of IAM are 
    1) users = Individual accounts of all people who use your AWS account
    2) Groups = Collection of IAM users.
    3) Policies = Defining Permissions (Deny/Allow) for action on AWS resources. 
    4) Roles = Temporary access without credentials.
* There are two types of users
   1) Root user = Having Full permissions
   2) IAM user = Having Limited permissions

## USERS
---------
* An IAM user is an entity that you create in your AWS account. The IAM user represents the human user or workload who uses the IAM user to interact with AWS resources. An IAM user consists of a name and credentials.
* For IAM users, we can anytime attach and detach the permissions/policies.
* You can share the root account access/admin access by creating IAM user.
* MFA is highly recommended for both root account and IAM account.
* There are 2 ways to access the AWS account
   | AWS console access      | Programmatic Access   |
   --------------------------|------------------------
   | Login using username/password | Login using Access keys and secret keys |
   