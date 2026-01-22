# AWS Identity and Access Management – Practice Tasks 

## Task 1: Create IAM User with Least Privilege

**Objective**

* Create an IAM user for a DevOps engineer with **only EC2 read-only access**

**Practice Points**

* Create IAM user
* Attach AWS managed policy: `AmazonEC2ReadOnlyAccess`
* Login using IAM user
* Verify user cannot create or delete EC2

**Learning Outcome**

* Least privilege principle
* Difference between read vs write permissions

---

## Task 2: IAM User + Inline Policy Restriction

**Objective**

* Allow a user to **start and stop EC2 instances**, but **not create or terminate**

**Practice Points**

* Create custom inline policy
* Use actions:

  * Allow: `ec2:StartInstances`, `ec2:StopInstances`
  * Deny: `ec2:RunInstances`, `ec2:TerminateInstances`

**Learning Outcome**

* Action-level permission control
* Custom IAM policy writing

---

## Task 3: IAM Group-Based Access Management

**Objective**

* Create groups for **Admin**, **Developer**, and **ReadOnly**

**Practice Points**

* Create 3 IAM groups
* Attach policies:

  * Admin → `AdministratorAccess`
  * Developer → EC2 + S3 limited access
  * ReadOnly → `ReadOnlyAccess`
* Add users to groups

**Learning Outcome**

* Why groups are better than attaching policies to users
* Scalable IAM design

---

## Task 4: IAM Password Policy Enforcement

**Objective**

* Enforce strong password rules for all IAM users

**Practice Points**

* Set password policy:

  * Minimum length
  * Uppercase, lowercase, number, special character
  * Password expiry
* Test with IAM user login

**Learning Outcome**

* Account-level security controls
* IAM security best practices

---

## Task 5: Enable MFA for IAM User

**Objective**

* Secure an IAM user using **Multi-Factor Authentication**

**Practice Points**

* Enable MFA (Virtual MFA)
* Test login with and without MFA
* Observe access restriction

**Learning Outcome**

* Importance of MFA
* Preventing credential compromise

---

## Task 6: S3 Bucket Access Using IAM Policy

**Objective**

* Allow a user to access **only one specific S3 bucket**

**Practice Points**

* Create S3 bucket
* Create IAM policy with:

  * Resource-level restriction
* Test access to allowed vs non-allowed buckets

**Learning Outcome**

* Resource-based permission control
* Secure data access

---

## Task 7: IAM Role for EC2

**Objective**

* Allow EC2 instance to access S3 **without access keys**

**Practice Points**

* Create IAM role for EC2
* Attach S3 access policy
* Attach role to EC2 instance
* Access S3 from EC2 using AWS CLI

**Learning Outcome**

* IAM roles vs IAM users
* Secure service-to-service access

---

## Task 8: Cross-Account IAM Role Access

**Objective**

* Allow IAM user from **Account A** to access S3 in **Account B**

**Practice Points**

* Create IAM role in Account B
* Configure trust relationship
* Assume role from Account A
* Access resources

**Learning Outcome**

* Cross-account access
* Trust policies vs permission policies

---

## Task 9: IAM Policy Condition with IP Restriction

**Objective**

* Allow AWS access **only from a specific IP address**

**Practice Points**

* Use `Condition` with `aws:SourceIp`
* Test login from allowed and non-allowed IPs

**Learning Outcome**

* Conditional access
* Network-based security in IAM

---

## Task 10: IAM Policy Simulator & Access Troubleshooting

**Objective**

* Debug permission issues using IAM Policy Simulator

**Practice Points**

* Create a user with limited permissions
* Simulate allowed and denied actions
* Identify missing permissions
* Fix policy

**Learning Outcome**

* IAM troubleshooting
* Real-world permission debugging

