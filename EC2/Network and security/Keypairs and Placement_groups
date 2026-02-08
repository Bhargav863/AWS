## Key Pairs

- A key pair is used to access an EC2 instance.
  - **Linux EC2**: Used for SSH authentication (no password by default).
  - **Windows EC2**: Used to decrypt the Administrator password.
- By default, no key pair exists in an AWS account.
- The extension of a key pair file is `.pem`.
- You can create multiple key pairs.
- One key pair can be associated with multiple EC2 instances.
- An EC2 instance can have only **one** key pair attached at a time.
- For **Windows EC2 instances**, each instance has a different Administrator password.
- A key pair cannot be changed directly after it is attached to an EC2 instance, but it can be **recovered or replaced** using supported recovery methods.
- Key pair = **Public key + Private key (PEM file)**.
- AWS stores the **public key**, and the customer stores the **private key**.

**Windows EC2 Instance**
- User: `Administrator`
- Authentication: Decrypted using PEM file
- Protocol: `RDP`
- Port: `3389`

**Linux EC2 Instance**
- User: `ec2-user`
- Authentication: PEM file
- Protocol: `SSH`
- Port: `22`

---

## Placement Groups

- Placement groups are used for clustering EC2 instances.
- By default, EC2 distributes instances across different underlying hardware to improve availability.
- If you want EC2 instances to be placed close together for performance reasons, you can use placement groups.
- There are **three types of placement groups**:

### 1. Cluster Placement Group
- Groups EC2 instances within the **same Availability Zone (AZ)**.
- Designed for **low latency and high network performance**.
- Provides **high performance but low availability**.

### 2. Spread Placement Group
- EC2 instances are placed on **distinct underlying hardware** to reduce the risk of simultaneous failures.
- Provides **high availability**.
- Best suited for **critical applications**.
- Supports a maximum of **7 EC2 instances per placement group per AZ**.

### 3. Partition Placement Group
- EC2 instances are divided into **logical partitions**, each running on separate hardware.
- Each partition can support **hundreds of EC2 instances**.
- You can create up to **7 partitions per AZ**.
- If one partition fails, only the EC2 instances in that partition are affected.

- Placement groups are recommended to use the **same EC2 instance type**.
- When launching an EC2 instance, you can choose which placement group the instance should belong to.
