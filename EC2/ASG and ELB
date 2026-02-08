## Auto Scaling Groups

- **Auto Scaling** automatically:
  - **Scale out** – Add EC2 instances
  - **Scale in** – Remove EC2 instances  
  based on demand.
- Auto Scaling Groups (ASG) scale out during **high/peak traffic** and scale in when traffic becomes **normal**.

### ASG Capacity Settings
- **Minimum Capacity**
  - The minimum number of EC2 instances ASG must maintain  
  - Example: `min = 2`

- **Maximum Capacity**
  - The maximum number of EC2 instances ASG can scale up to  
  - Example: `max = 6`

- **Desired Capacity**
  - The number of EC2 instances you want to launch initially.

---

## Types of Scaling Options

1. **Manual Scaling**
   - Manually modify the minimum, maximum, or desired number of instances.

2. **Scheduled Scaling**
   - Scale in or scale out based on a **time-based schedule**.

3. **Dynamic Scaling**
   - Automatically scales based on **load/traffic metrics**, such as:
     - CPU utilization
     - Network traffic
     - Request count

---

## Launch Template / Launch Configuration

- A **Launch Template** defines how EC2 instances are launched.
- It includes:
  - Custom AMI
  - Instance type
  - Volumes
  - Security Groups
  - Key pair
  - Tags
  - Applications and configurations
- Launch Template is **attached to an Auto Scaling Group**.

---

## Elastic Load Balancer (ELB)

- ELB distributes incoming traffic across **multiple EC2 instances** within an Availability Zone.
- ELB is accessed using a **DNS name or URL**.
- You **cannot log in** to an ELB.
- ELB has IP addresses, but they **change dynamically**.
- ELB is **fully managed by AWS**.

---

## Types of Load Balancers

### 1. Application Load Balancer (ALB)

- Works at **Layer 7**
- Default and recommended load balancer
- Supports **HTTP and HTTPS**
- Best suited for **microservices-based applications**

---

### 2. Network Load Balancer (NLB)

- Works at **Layer 4**
- Latest-generation load balancer
- Supports **TCP and UDP**
- Used for **extreme high performance**
- Provides **one static IP per Availability Zone**

---

### 3. Classic Load Balancer (CLB)

- Previous-generation load balancer
- Supports **HTTP, HTTPS, and TCP** protocols

---

### 4. Gateway Load Balancer (GWLB)

- Latest-generation load balancer
- Works at **Layer 3**
- Used to deploy and manage **third-party network virtual appliances**
  - Examples: Firewalls, intrusion prevention systems
- Uses **GENEVE protocol (port 6081)**

---

## Routing Features of Application Load Balancer

1. Host-based routing  
2. Path-based routing  
3. String-based routing  

- Target Groups are created for different requests.
- Based on routing rules, ELB forwards traffic to the appropriate **Target Group**.

---

## Types of IP Addresses

### Public IP

- Accessible from the **Internet**
- Optional
- **Dynamic**
- Assigned by AWS
- Changes when the EC2 instance is **stopped and started**

---

### Private IP

- **Not accessible** from the Internet
- **Mandatory**
- **Static**
- Used within:
  - VPC
  - VPN connections

---

### Elastic IP (EIP)

- Similar to Public IP but **static**
- Does **not change** when the EC2 instance is stopped and started
- Up to **5 Elastic IPs are free**
- Must be **associated** with an EC2 instance
- Unused or **idle EIPs are charged**

---

## Instance Metadata & User Data

### Instance Metadata
- Information about the EC2 instance itself
  - Example: Instance ID, IP addresses, security groups

### User Data
- A script provided by the user that runs at **instance boot time**
- Runs **only once** during the first launch
- To edit user data:
  - Stop the EC2 instance
  - Modify the user data
  - Start the instance
