# AWS IAM Tasks

## 1. Create an Account Alias and Bookmark the IAM User Sign-In Link

## 2. Create Your Own IAM User with the Administrator Policy Attached

## 3. Set Up MFA for the IAM User You Created (Your Own Name)

## 4. Set Up MFA for the Root Account (Security Credentials)

**Note:** Your Google Authenticator should have only 2 accounts: **IAM and ROOT**. Do not delete the app.

**Sign out from the Root account and log in as the IAM user you just created. From now onwards, always log in using the IAM user and the bookmarked IAM sign-in link.**

---

## 5. Create Another Sample IAM User (`testuser1`)

## 6. Attach and Detach Policies for the Sample IAM User (`testuser1`)

**Do not perform these operations on your main IAM user.**

* Attach 11 managed policies to the IAM user and determine the maximum number of managed policies that can be attached to an IAM user.
* Perform the same test for an IAM group and determine the maximum number of managed policies that can be attached to a group.

## 7. Create 2 or 3 IAM Groups and Attach Users to the Groups

* Remove users from the groups.
* Remove permissions from the groups.
* Create an IAM user and attach 10 policies to the user.
* Create a group and attach 10 policies to the group.
* Add the IAM user to the group.
* Check how many policies the IAM user has in total.

## 8. Disable Console Access for the Test IAM User

Try to log in using the IAM user after disabling console access and check what error you receive.

## 9. Reset the IAM User Password

Try to log in using the reset password.

## 10. Create an Access Key and Secret Access Key for the Test IAM User

## 11. Deactivate the Access Keys

## 12. Delete the Access Keys

## 13. Check Group Access Advisor and IAM User Last Accessed Information

## 14. Delete the Sample IAM Users

**Do not delete your own IAM user.**

## 15. Delete the IAM Groups

## 16. Sign Out of the IAM User

---

## 17. Create a Role and Assign Permissions

### Scenarios

* EC2
* Lambda
* Switch Role

## 18. Create 2 IAM Users (`test1` and `test2`)

### Assign Permissions to `test1`

Assign:

```text
IAMFullAccess
```

Log out and log in as `test1` and verify the IAM permissions.

### Assign Permissions to `test2`

Assign:

```text
IAMReadOnlyAccess
```

Log out and log in as `test2` and verify the IAM permissions.

## 19. Create an IAM User (`test3`)

This user should only be able to perform the following operations:

* Create users
* List users
* Get users
* Get groups
* Create groups
* List groups
* Update users
* Update groups

Attach this policy to the `test3` user.

Log out and log in as `test3` and verify what permissions `test3` has and what actions `test3` cannot perform.
