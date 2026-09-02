# AWS Global Infrastructure

## AWS Global Infrastructure

- AWS has a **Global Infrastructure**.
- A **Region** is a geographical area where AWS has its data centers.
- Example: **AWS Region = Mumbai**.
- ~39+ Regions are available in AWS.
- A Region contains multiple Availability Zones (AZs).
- A Region contains multiple data centers.
- An Availability Zone (AZ) is simply a data center.
- Servers = Instances.
- Servers/Instances are placed in AZs.
- A Region contains multiple AZs.

### Regions and Availability Zones

Example:

```text
Mumbai = ap-south-1

AZs:
    ap-south-1a
    ap-south-1b
    ap-south-1c
```

- Regions and AZs are managed by AWS.
- AZs can communicate with each other by default.
- AZ networks are interconnected.
- Low latency = Good → Quick response, approximately 1 sec.
- High latency = Bad → Late response, approximately 3 secs.
- Regions do not communicate with each other by default. If required, communication can be configured.

### Best Practice

- Distribute instances across multiple AZs.
- This significantly reduces the chance of the entire application going down if one AZ goes down.
- A single AZ can consist of multiple data centers.

### Load Balancer

- Load Balancers distribute traffic to multiple EC2 instances across AZs.
- A Load Balancer is specific to a **Region**, not to a single AZ.

### EC2 Instance

- An EC2 instance is specific to a **Region and AZ**.

### Example AZ Locations

```text
Region: Mumbai

1a → Dadar, Andheri, Airoli
1b → Thane, Bandra, Kalyan
1c → Kurla, Juhu, Powai
```

---

# AWS Regions and Availability Zones Example

```text
                         AWS Region: Mumbai
                   ┌─────────────────────────────┐
                   │                             │
                   │   AZ: ap-south-1a           │
                   │   ┌─────────────────────┐   │
                   │   │ EC2  EC2            │   │
                   │   │ EC2  EC2            │   │
                   │   └─────────────────────┘   │
                   │             │               │
                   │             │ Network       │
                   │             │               │
                   │   AZ: ap-south-1b           │
                   │   ┌─────────────────────┐   │
                   │   │ EC2  EC2            │   │
                   │   │ EC2  EC2            │   │
                   │   └─────────────────────┘   │
                   │             │               │
                   │             │               │
                   │   AZ: ap-south-1c           │
                   │   ┌─────────────────────┐   │
                   │   │ EC2  EC2            │   │
                   │   │ EC2  EC2            │   │
                   │   └─────────────────────┘   │
                   │                             │
                   └─────────────────────────────┘

                         Region = Mumbai
```

## Communication Between Regions

```text
Region: Mumbai                         Region: Ireland

┌─────────────────────┐                ┌─────────────────────┐
│ AZ: 1a   AZ: 1b     │                │ AZ: 1a   AZ: 1b     │
│                     │                │                     │
│ AZ: 1c              │                │ AZ: 1c   AZ: 1d     │
└─────────────────────┘                └─────────────────────┘

        Network                              Network
           X                                  │
        Default                              │
     communication                          │
       not enabled                           │
```

---

# Virtual Private Cloud (VPC)

- **VPC = Virtual Private Cloud.**
- A VPC is created within an AWS Region.
- EC2 instances can be launched inside a VPC.
- VPCs are isolated from each other by default.
- Communication between VPCs is not available by default.
- VPC-to-VPC communication can be configured when required.

### VPC Example

```text
                         AWS Public Cloud
                    ┌────────────────────────┐
                    │                        │
                    │        VPC             │
                    │   ┌──────────────┐     │
                    │   │              │     │
                    │   │ EC2  EC2     │     │
                    │   │ EC2  EC2     │     │
                    │   │              │     │
                    │   └──────────────┘     │
                    │                        │
                    │        VPC             │
                    │   ┌──────────────┐     │
                    │   │ EC2  EC2     │     │
                    │   │ EC2  EC2     │     │
                    │   └──────────────┘     │
                    │                        │
                    └────────────────────────┘
```

### VPC Communication

```text
VPC 1  ──────── X ────────  VPC 2
                    Default:
                 No communication

VPC 3  ──────── X ────────  VPC 4
                    Default:
                 No communication
```

- VPCs are logically isolated.
- If communication between VPCs is required, it must be configured.

---

# Default VPC

- Every AWS Region has a **default VPC**.
- The default VPC is created automatically by AWS.
- The diagram represents multiple VPCs within an AWS Region.

```text
                         AWS
              ┌──────────────────────┐
              │       Region         │
              │                      │
              │       VPC            │
              │   ┌──────────────┐   │
              │   │     AZ       │   │
              │   │    EC2       │   │
              │   └──────────────┘   │
              │                      │
              │       AZ             │
              │   ┌──────────────┐   │
              │   │    EC2       │   │
              │   └──────────────┘   │
              │                      │
              │       AZ             │
              │   ┌──────────────┐   │
              │   │    EC2       │   │
              │   └──────────────┘   │
              │                      │
              └──────────────────────┘
```

- The relationship can be understood as:

```text
AWS
└── Region
    └── VPC
        └── Availability Zones
            └── EC2 Instances
```

---

# Key Points

- **Region** = Geographical area.
- **Availability Zone (AZ)** = AWS infrastructure location within a Region.
- **Region** contains multiple AZs.
- **EC2 Instance** is launched in a specific Region and AZ.
- **AZs within a Region** are interconnected and can communicate by default.
- **Regions** are isolated from each other by default.
- **VPC** provides logical network isolation within an AWS Region.
- **VPCs** are isolated from each other by default.
- **Load Balancer** can distribute traffic across multiple AZs within a Region.
