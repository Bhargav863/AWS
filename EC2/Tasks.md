# Tasks – EC2

This document outlines the **end-to-end tasks involved in launching and managing EC2 instances**, including **Launch Templates** and important operational behaviors.

---

## 1. Create a Key Pair
- Create a **key pair (.pem file)**.
- This key pair is used to securely connect to EC2 instances.
- Download and store the `.pem` file securely (cannot be downloaded again).

---

## 2. Create a Security Group
- Create a **Security Group** (acts as a virtual firewall).
- Update **Inbound Rules** to allow required traffic:

| Protocol | Port | Use Case |
|--------|------|----------|
| RDP | 3389 | Windows instances |
| SSH | 22 | Linux instances |
| HTTP | 80 | Web traffic |
| HTTPS | 443 | Secure web traffic |
| MySQL | 3306 | Database access |

> Security Groups are **stateful** and work at the **instance level**.

---

## 3. Launch a Red Hat Linux EC2 Instance
- Choose **Red Hat Enterprise Linux (RHEL)** AMI.
- Select instance type (example: `t2.micro`).
- Attach:
  - Key pair
  - Security Group
- Launch the instance.
- Connect using:
  - **PuTTY** (Windows)
  - **MobaXterm** (Windows)
  - **SSH** (Linux/Mac)

---

## 4. Stop and Start the Instance
- Stop the EC2 instance.
- Start it again.
- Observe:
  - **Private IP** → Does NOT change
  - **Public IP** → Changes (if Elastic IP is not used)

---

## 5. Reboot the Instance
- Reboot the EC2 instance.
- Observe:
  - **Private IP** → Does NOT change
  - **Public IP** → Does NOT change

---

## 6. Allocate and Associate an Elastic IP (EIP)
- Allocate an **Elastic IP** from AWS.
- Associate the Elastic IP with the EC2 instance.
- Elastic IP provides a **static public IP**.

---

## 7. Stop / Start or Reboot with Elastic IP
- Stop and start the EC2 instance.
- Reboot the instance.
- Observe:
  - **Public IP remains the same** (because of Elastic IP)

---

## 8. De-associate and Release Elastic IP
- De-associate the Elastic IP from the EC2 instance.
- Release the Elastic IP back to AWS.
- This avoids **unnecessary billing charges**.

---

## 9. Launch Templates
- Create a **Launch Template** that includes:
  - AMI
  - Instance type
  - Key pair
  - Security Group
  - Storage configuration
  - Tags
- Launch EC2 instances using the **Launch Template**.
- Verify instances are created correctly.
- Delete the launched instances.
- Delete the Launch Template.

> Launch Templates provide **standardization**, **automation**, and **reusability**.

---

## 10. Instance Shutdown Behavior
- Review the **Shutdown behavior** setting:
  - `Stop`
  - `Terminate`
- Shut down the instance from the OS.
- Observe whether the instance:
  - Stops
  - Terminates
- Change shutdown behavior to **Terminate**.
- Shut down again and observe the difference.

---

## 11. Review EC2 Actions Menu
- Explore available options under **Actions**, such as:
  - Instance State
  - Image and Templates
  - Security
  - Networking
  - Monitor and Troubleshoot
  - Instance Settings

---

## 12. Terminate EC2 Instances
- Terminate the EC2 instances.
- Verify:
  - Instance is permanently deleted
  - Root volume is deleted (default behavior)

---

## 13. Shutdown Behavior Validation
- Enable shutdown behavior as:
  - **Stop**
  - **Terminate**
- Log in to the EC2 instance.
- Run OS-level shutdown command.
- Observe:
  - Instance stops when set to **Stop**
  - Instance terminates when set to **Terminate**

---

- Launch Templates simplify and standardize instance creation.
- Shutdown behavior controls what happens when OS is shut down.
