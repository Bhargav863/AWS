# Images (AMI)

- A **copy of an operating system (OS)** is called an **image**.
- An image in AWS is called an **AMI (Amazon Machine Image)**.
- An AMI is a **template** used to launch EC2 instances.
- **AMI = OS or OS + Applications + Configuration**
- An AMI contains all configurations done on the original instance
  (OS settings, installed software, patches, etc.).
- AMIs are **reusable**: you can create multiple EC2 instances from the same AMI.
- AMIs are **regional** and **not tied to a specific Availability Zone**.
- By default, AMIs are **private**.
  - You can make them **public** or **share them with other AWS accounts** using the AWS account ID.
- AMIs can be **copied from one region to another** within the same account.
- Public AMIs are available through:
  - **AWS Marketplace**
  - **Community AMIs**
  - **AWS-provided AMIs** (for example, Amazon Linux)

---

## Types of AMIs

- **Custom AMIs**
  - Manually created by users from their EC2 instances

- **Golden AMIs**
  - Standardized, pre-approved images
  - Usually created and maintained automatically

- **EC2 Image Builder**
  - Used to **automate AMI creation**
  - Commonly used to build and manage **Golden AMIs**

---

## AMI Storage & Backing

- Most AMIs are **backed by EBS volumes**.
- AMI structure:
    **AMI → Snapshot(s) → EBS Volume(s)**
- The root device of an AMI is typically an **EBS root volume snapshot**.

---

## Creating an AMI

- You **do not need to stop** an EC2 instance to create an AMI.
- However, it is **recommended to stop the instance** to ensure data consistency
(especially for production workloads).
