# AWS IAM Tasks

* **Task 1:** Create an Account Alias and bookmark the IAM User Sign-In Link.

* **Task 2:** Create your own IAM user with the Admin policy attached.

* **Task 3:** Set up MFA for the IAM user you created (your own name).

* **Task 4:** Set up MFA for the Root account (Security Credentials).

  **Note:** Your Google Authenticator should have only 2 accounts: **IAM and ROOT**. Do not delete the app.

  **Sign out from the Root account and log in as the IAM user you just created. From now onwards, always log in using the IAM user and the bookmarked IAM sign-in link.**

* **Task 5:** Create another sample IAM user (`testuser1`).

* **Task 6:** Attach and detach policies for the sample IAM user (`testuser1`).

  **Do not perform these operations on your main IAM user.**

  * Attach 11 managed policies to the IAM user and determine the maximum number of managed policies that can be attached to an IAM user.
  * Perform the same test for an IAM group and determine the maximum number of managed policies that can be attached to a group.

* **Task 7:** Create 2 or 3 IAM groups and attach users to the groups.

  * Remove users from the groups.
  * Remove permissions from the groups.
  * Create an IAM user and attach 10 policies to the user.
  * Create a group and attach 10 policies to the group.
  * Add the IAM user to the group.
  * Check how many policies the IAM user has in total.

* **Task 8:** Disable console access for the test IAM user.

  Try to log in using the disabled IAM user and check what error you receive.

* **Task 9:** Reset the IAM user password.

  Try to log in using the reset password.

* **Task 10:** Create an Access Key and Secret Access Key for the test IAM user.

* **Task 11:** Deactivate the Access Keys.

* **Task 12:** Delete the Access Keys.

* **Task 13:** Check Group Access Advisor and IAM User Last Accessed information.

* **Task 14:** Delete the sample IAM users.

  **Do not delete your own IAM user.**

* **Task 15:** Delete the IAM groups.

* **Task 16:** Sign out of the IAM user.

* **Task 17:** Create a role and assign permissions for the following scenarios:

  * EC2
  * Lambda
  * Switch Role

* **Task 18:** Create 2 IAM users (`test1` and `test2`).

  * **test1:** Assign `IAMFullAccess`.
  * Log out and log in as **test1** and verify the IAM permissions.
  * **test2:** Assign `IAMReadOnlyAccess`.
  * Log out and log in as **test2** and verify the IAM permissions.

* **Task 19:** Create an IAM user (`test3`).

  This user should only be able to perform the following operations:

  * Create users
  * List users
  * Get users
  * Get groups
  * Create groups
  * List groups
  * Update users
  * Update groups

  Attach this policy to the **test3** user.

  Log out and log in as **test3** and verify what permissions **test3** has and what actions **test3** cannot perform.
