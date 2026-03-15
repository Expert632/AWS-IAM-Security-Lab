AWS IAM Security Lab

   Learn Cloud Identity & Access Management the Practical Way

This hands-on lab demonstrates how to **secure access in the AWS Cloud using Identity and Access Management (IAM)**.

In modern cloud environments, **security is not only about networks and firewalls**.
The **first security layer is identity** — *who can access what*.

In this lab, we will build a **secure IAM architecture step-by-step**, following security best practices used by real **Cloud and DevSecOps engineers**.

By the end of this lab you will understand how to:

* Create secure IAM users
* Organize access using IAM groups
* Write custom JSON permission policies
* Enforce **least-privilege access**
* Protect accounts using **Multi-Factor Authentication (MFA)**
* Allow machines (EC2) to securely access AWS services using **IAM Roles**

This lab is ideal for students learning:

* Cloud Security
* AWS Fundamentals
* DevSecOps
* Identity Management

---

# 🧠 What You Will Learn

This lab teaches the **core security concepts used in AWS IAM**:

| Concept         | Explanation                                      |
| --------------- | ------------------------------------------------ |
| IAM User        | Identity used by a human user                    |
| IAM Group       | Collection of users sharing the same permissions |
| IAM Policy      | JSON document defining permissions               |
| Least Privilege | Giving only the permissions required             |
| MFA             | Extra authentication layer for security          |
| IAM Role        | Temporary permissions for AWS services (ex: EC2) |

---

# 🏗 Lab Architecture

In this lab we implement the following **secure access design**:

```
IAM Policy
     ↓
IAM Group
     ↓
IAM User
     ↓
MFA Enabled

EC2 Instance
     ↓
IAM Role
     ↓
Secure AWS Service Access
```

This architecture reflects **real production security practices**.

---

# ⚙️ Lab Steps

## Step 1 — Login to AWS Console

First connect to the **AWS Management Console**.

Then navigate to the IAM dashboard.

This is the central place where AWS manages:

* users
* groups
* roles
* policies

**Navigation**

```
AWS Console
   → Services
      → IAM
```

The IAM Dashboard gives a **global view of cloud identities and security status**.

---

# 👥 Step 2 — Create an IAM Group

Instead of giving permissions directly to users, best practice is to **assign permissions to groups**.

Groups make administration **simpler and more secure**.

Example:

```
Developers Group
Admins Group
ReadOnly Group
```

Users simply join the group to receive permissions.

This follows the **principle of centralized permission management**.

---

# 📜 Step 3 — Create a Custom JSON Policy

Policies define **what actions are allowed or denied**.

AWS policies use **JSON format**.

Example structure:

```json
{
 "Version": "2012-10-17",
 "Statement": [
   {
     "Effect": "Allow",
     "Action": [
       "s3:ListBucket"
     ],
     "Resource": "*"
   }
 ]
}
```

This policy allows users to **list S3 buckets**.

Using **custom policies** demonstrates real security skills because you control:

* specific actions
* specific services
* specific resources

---

# 🔗 Step 4 — Attach the Policy to the Group

Once the policy is created, we attach it to the **IAM Group**.

```
Policy
   ↓
IAM Group
   ↓
Users inherit permissions
```

This is a **scalable permission model** used in enterprises.

---

# 👤 Step 5 — Create an IAM User

Now we create a user who will access AWS.

Example:

```
User: developer-user
```

Users can access AWS using:

* AWS Console
* CLI
* API

Best practice is **never to use the root account** for daily operations.

IAM users provide **controlled and traceable access**.

---

# ➕ Step 6 — Add the User to the Group

Instead of manually assigning permissions, we **add the user to the IAM group**.

```
IAM Group
   ↓
Permissions
   ↓
IAM User
```

Now the user automatically inherits the group permissions.

This is much easier to manage when there are **many users**.

---

# 🔑 Step 7 — Enable MFA for the User

Security best practice requires enabling **Multi-Factor Authentication (MFA)**.

MFA requires **two authentication factors**:

```
Password
+
Temporary Code
```

The code can come from apps like:

* Google Authenticator
* Microsoft Authenticator

Benefits:

* prevents account takeover
* protects against stolen passwords

MFA is **strongly recommended for all privileged users**.

---

# 🖥 Step 8 — Create an IAM Role for EC2

Machines should **never store permanent credentials**.

Instead AWS uses **IAM Roles**.

An IAM Role provides **temporary credentials** to AWS services.

Example:

```
EC2 Instance
     ↓
IAM Role
     ↓
Access to S3 / DynamoDB / etc
```

Advantages:

* no secret keys stored
* automatic credential rotation
* secure machine access

This is the **industry standard approach** for secure cloud workloads.

---

# 🛡 Security Best Practices Demonstrated

This lab follows important AWS security principles:

✔ Principle of Least Privilege
✔ Use of IAM Groups
✔ Custom Policies
✔ MFA Protection
✔ Role-Based Access for Services
✔ Avoid Root Account Usage

These practices are used by **Cloud Security Engineers and DevSecOps teams**.

---

# 🎯 Skills Demonstrated

Completing this lab demonstrates practical knowledge of:

* AWS Identity and Access Management
* Cloud Security Architecture
* Access Control Design
* DevSecOps Security Fundamentals

These skills are essential for roles such as:

* Cloud Security Engineer
* DevSecOps Engineer
* AWS Cloud Engineer
* Cybersecurity Engineer

---

# 🚀 Why This Lab Matters

Misconfigured identities are one of the **main causes of cloud security breaches**.

Understanding IAM is therefore **one of the most important cloud security skills**.

This lab demonstrates your ability to:

* design secure access
* apply AWS best practices
* protect cloud infrastructure

---


→ C’est ce type de README qui **impressionne vraiment les recruteurs Cloud / DevSecOps**.
