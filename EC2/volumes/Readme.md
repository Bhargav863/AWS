# Volumes

- Volumes are classified into **2 types**:
  1. **EBS Volumes**
  2. **Instance Store Volumes (ISV)**

---

## Elastic Block Store (EBS)

- EBS is **permanent (persistent) storage**.
- If you **stop and start** an EC2 instance, **data is not lost**.
- Maximum EBS volume size is **16 TiB**.
- EBS is **billable**.

---

## Types of EBS Volumes

- **General Purpose SSD** (`gp2`, `gp3`)
- **Provisioned IOPS SSD** (`io1`, `io2`) – High performance
- **Throughput Optimized HDD** (`st1`) – For frequently accessed, throughput-intensive data at lower cost
- **Cold HDD** (`sc1`) – For infrequently accessed data at lower cost
- **Magnetic (standard)** – Previous generation (largely deprecated)

> **More performance = More cost**

---

## EBS Performance & IOPS

- `gp3` is the **default EBS volume type** for new volumes.
- **IOPS** = Input/Output Operations Per Second.
- `gp3`, `io1`, and `io2` allow **configurable IOPS**.
- Higher IOPS → **higher cost**.
- `gp2` IOPS are **not directly configurable**:
  - Baseline performance is **3 IOPS per GB of volume size** (not RAM).
- `st1` and `sc1` **cannot be used as root volumes**.
- **Root volumes** support: `gp2`, `gp3`, `io1`, `io2`, and magnetic (standard).
- **Additional (data) volumes** support all EBS volume types.
- `io1` and `io2` support **Multi-Attach**:
  - Can be attached to **up to 16 EC2 instances**
  - Instances must be **Nitro-based** and in the **same Availability Zone**

---

## Instance Store Volumes

- Instance store volumes are **temporary (ephemeral) storage**.
- If you **stop/start or terminate** the EC2 instance, **data is lost**.
- Instance store volumes are **free of charge**.
- Attached **automatically based on the instance type**.
- If you **reboot** the instance, data **is not lost**.
- Provides **very high performance**.
- Risk of **data loss if hardware fails**.

---

## Delete on Termination Behavior

- By default, when an EC2 instance is **terminated**, the **root volume is deleted**
  because **“Delete on termination”** is enabled.
- To retain the root volume, **disable “Delete on termination”** during launch or later.
- **Additional EBS volumes** are **not deleted by default** when the instance is terminated.

---

## Snapshots

- A **snapshot** is a **point-in-time backup** of an EBS volume.
- Snapshots are **incremental** backups.
- Flow:
    **EBS Voulme --> snapshot --> EBS Volume**
- You **cannot attach a snapshot directly** to an EC2 instance.
- You must **create a volume from the snapshot** and then attach it.
- You **cannot log in** to a snapshot.
- Snapshots are stored in **AWS-managed S3**.
- Snapshots are **regional** (not tied to a specific AZ).
- By default, snapshots are **private**, but they can be shared or made public.
- Snapshots can be **copied between regions** in the same account.
- Snapshots can be **shared across AWS accounts**.
- EBS volumes **cannot be moved directly** between AZs:
- Create a snapshot → Create a new volume in the target AZ.
- **Stopping the EC2 instance is not required** to create a snapshot
(though stopping is recommended for consistency in some workloads).

---

## Data Lifecycle Manager (DLM)

- Used to **automate and schedule snapshots**.
- Volumes are identified using **tags**.
- You can define **retention policies**
(for example: keep snapshots for 7 days or 10 days, then delete).

---

## EBS Snapshot Archive Tier

- Snapshots can be moved from **Standard tier** to **Archive tier**.
- Archive tier is **up to 75% cheaper**.
- Retrieval from Archive tier takes **24 to 72 hours**.

---

## Recycle Bin

- Allows recovery of **deleted EBS snapshots**.
- Retention period can be set from **1 day to 1 year**.

---

## Encryption

- **EBS volumes and snapshots can be encrypted** using **AWS KMS**.
- Default encryption depends on **account-level settings**
(accounts may have encryption enabled by default).
- Encryption behavior:
- **Unencrypted volume → Unencrypted snapshot**
- **Encrypted volume → Encrypted snapshot**
- **Unencrypted snapshot → Encrypted snapshot** (using the **Copy** option)
- **KMS (Key Management Service)** stores and manages encryption keys.
- **Encrypted snapshots cannot be made public**.
- Encrypted snapshots **can be shared with other AWS accounts**
if proper **KMS permissions** are granted.
