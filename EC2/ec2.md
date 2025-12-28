# EC2

- **EC2** stands for **Elastic Compute Cloud**.
- EC2 is a web service that provides secure and resizable compute power in the cloud.
- **Resizable**
  1. **Scale out / Scale in** = **Elasticity** = increasing/decreasing the number of instances
  2. **Scale up / Scale down** = **Scalability** = increasing/decreasing the capacity of the server
- EC2 is a **regional service**.
- We can perform the following actions on EC2:
  1. Launch
  2. Start
  3. Stop
  4. Reboot
  5. Terminate
- **Pay-as-you-go pricing model**: AWS charges for every one hour.
- **750 hours are free per month**.
- Example:
  1. EC2 instance used for 5 minutes → Terminated  
  2. EC2 instance used for 5 minutes → Terminated  
  AWS will charge for **2 hours** (1 hour for each instance).

---

## Pricing Models in AWS

### 1. On-Demand Instances
- Fixed price (hourly)
- Pay for what you use (charged hourly)
- No commitment
- No upfront payment
- No predictable usage

---

### 2. Reserved Instances
- Long-term commitment for **1 or 3 years**
- Upfront payment
- AWS provides up to **70–75% (~72%) discount**
- There are **2 types of Reserved Instances**:
  1. **Convertible RI**  
     - You can change the instance capacity at any time  
     - More than **60% discount**
  2. **Standard RI**  
     - You cannot change the capacity  
     - Up to **75% discount**

---

### 3. Spot Instances
- Bidding/auction-based instances
- Up to **90% discount**
- Huge capacity at a cheaper price

---

### 4. Dedicated Host
- You get your own **dedicated physical host** in AWS
- Used when you want physical servers with VMs on the same machine

---

### 5. Savings Plan
- Flexible pricing model that provides savings over on-demand pricing

---

## EC2 Instance Types

### 1. General Purpose Instances
- Provide a balance of compute and memory
- Suitable for:
  - Web servers
  - Databases
  - Development and testing environments

---

### 2. Compute Optimized Instances
- More CPUs
- Higher compute-to-memory ratio
- Suitable for:
  - Gaming applications
  - High-performance web servers

---

### 3. Memory Optimized Instances
- More memory for applications
- Suitable for memory-intensive workloads

---

### 4. Storage Optimized Instances
- More storage
- Used for applications that require high, sequential read and write access to large databases

---

### 5. Accelerated Computing
- Instances come with GPUs
- GPUs provide higher computing power compared to CPUs

---

### Instance Type = CPU + Memory

- `t2.micro` = 1 GB RAM + 2 vCPUs
- `t2.small` = 2 GB RAM + 2 vCPUs
- `t2.medium` = 4 GB RAM + 2 vCPUs
- `t2.xlarge` = 16 GB RAM + 8 vCPUs

---

## Changing Instance Type
- Downtime is required to change the instance type
- You must stop the instance before changing it
- No data loss occurs because data is stored in volumes

---

## Status Checks

### Types of Status Checks
1. **Instance status check** → Hardware check
2. **System status check** → Software check

### Results
- **2/2 checks passed** → You can log in
- **1/2 checks passed** → You cannot log in
- **0/2 checks passed** → You cannot log in

- Status checks are performed by AWS.
- If you get **1/2 or 0/2 checks passed**, stop the EC2 instance and start it again.