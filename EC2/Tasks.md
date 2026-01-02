# AWS EC2, AMI, Volumes & Load Balancer Lab 🖥️☁️

[![AWS](https://img.shields.io/badge/AWS-EC2-blue?logo=amazon-aws)](https://aws.amazon.com/ec2/)
[![Linux](https://img.shields.io/badge/Linux-red?logo=linux)](https://www.linux.org/)
[![ELB](https://img.shields.io/badge/Load_Balancer-green)](https://aws.amazon.com/elasticloadbalancing/)

This repository contains **step-by-step lab tasks** to practice **AWS EC2, AMI, EBS Volumes, and Load Balancers**.

---

## Table of Contents

- [EC2 Basics](#ec2-basics)
- [AMI Tasks](#ami-tasks)
- [EBS Volumes](#ebs-volumes)
- [Load Balancer Tasks](#load-balancer-tasks)
- [Notes](#notes)

---

## EC2 Basics

- [ ] Create a **Key Pair** (.pem file)
- [ ] Create a **Security Group** and add inbound rules:
  - Windows RDP → `3389`
  - Linux SSH → `22`
  - HTTP → `80`
  - HTTPS → `443`
  - MySQL → `3306`
- [ ] Launch **RedHat Linux EC2** → connect using PuTTY or MobaXterm
- [ ] Stop & Start → observe **private & public IP changes**
- [ ] Reboot → observe **private & public IP**
- [ ] Allocate **Elastic IP (EIP)** → associate with EC2
- [ ] Reboot / Stop & Start → verify public IP does **not change**
- [ ] De-associate & release EIP (avoid billing)
- [ ] Create **Launch Template** → launch EC2 from template → delete template
- [ ] Explore **Shutdown Behavior**:
  - Stop
  - Terminate
  - Observe differences
- [ ] Review **Actions** options
- [ ] Terminate EC2 instances
- [ ] Enable shutdown behavior = stop & terminate → shutdown → observe

---

## AMI Tasks

### Step 1 – Prepare EC2 Instance

- [ ] Launch EC2 instance
- [ ] Create files and install software on instance
- [ ] Verify files exist

### Step 2 – AMI Creation & Copy

- [ ] Create AMI from instance
- [ ] Launch instance from AMI → verify files exist
- [ ] Copy AMI to **another region** (Northern Virginia)
- [ ] Encrypt AMI during copy → launch instance → verify root EBS encrypted
- [ ] Copy encrypted AMI to same / different region

### Step 3 – Snapshot Tasks

- [ ] Copy snapshot to another region → verify → delete snapshot
- [ ] Encrypt snapshot → share with another AWS account
- [ ] Share AMI & snapshot to another account
- [ ] Create AMI from snapshot
- [ ] Delete snapshot → then AMI → observe result
- [ ] Delete AMI → then snapshot → observe result
- [ ] Delete snapshot → restore via **Recycle Bin**

### Step 4 – Lifecycle & Image Builder

- [ ] Data Lifecycle Manager:
  - Check UTC time
  - Create policy
  - Verify snapshot creation
  - Delete policy
- [ ] Optional: EC2 Image Builder
  - Create Golden AMI
  - Delete pipeline, recipes, configs, AMIs

---

## EBS Volumes

- [ ] Launch **4 EC2 instances**:
  - 2 in `ap-south-1a`
  - 2 in `ap-south-1b`

### Cross Task

- [ ] Create additional volumes → attach to instances
- [ ] Detach root volume from **EC2-1a** → attach to another EC2 in **same AZ** as root

### Volume Management

- [ ] Increase **root volume size**
- [ ] Add **additional EBS volume** → make available to users
- [ ] Detach & attach volumes:
  - Root volume to another EC2 as **root**
  - Root volume to another EC2 as **additional volume**
- [ ] Handle **lost PEM file scenario**
- [ ] Snapshot (Mumbai) → copy to Ireland → create volume → attach
- [ ] Extend existing Linux volume
- [ ] Create new additional Linux volume
- [ ] Lifecycle Manager policy:
  - Verify UTC snapshots
  - Tag volumes
  - Delete policy
- [ ] Cleanup: terminate EC2, delete additional volumes, lifecycle policy, copied snapshots

---

## Load Balancer (ELB) Tasks

- [ ] Launch 2 EC2 instances with **user data**
- [ ] Security Group:
  - Allow HTTP (80) from **My IP**
  - Keep default “all traffic” rule
- [ ] Access EC2 public IP → verify website works
- [ ] Create **Load Balancer**:
  - Health check path: `/index.html`
- [ ] Create **Target Group (TG)** → register targets
- [ ] Access **ELB DNS** → verify targets healthy
- [ ] Enable **stickiness** → test
- [ ] Configure **path-based routing**:
  - 4 EC2 instances:
    - 2 → `/index.html` → TG1
    - 2 → `/admin` → TG2
  - Load Balancer → Listeners → Edit rules → Add path `/admin` → forward to `Admin_TG`
- [ ] Review all **ELB & TG actions**
- [ ] Stop one EC2 → access ELB → verify website works
- [ ] Terminate all EC2, ELB, Target Groups

---

## Notes

- Snapshots & volumes → **tag properly**
- Verify **shutdown behavior**
- Elastic IP → **release after use**
- Encrypted AMI → root EBS is encrypted, works normally

---
