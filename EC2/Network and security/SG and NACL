## Security Groups

- A Security Group acts as a **firewall for EC2 instances** and controls inbound and outbound traffic.
  - **Security Group = Firewall for EC2 instances**
- Security Groups have **two types of rules**:
  1. **Inbound rules** – Control incoming traffic to the EC2 instance.
  2. **Outbound rules** – Control outgoing traffic from the EC2 instance.
- By default:
  - **All inbound traffic is denied**
  - **All outbound traffic is allowed**
- Common protocols and ports:
  - **RDP** – Port `3389` (used to log in to Windows EC2 instances)
  - **SSH** – Port `22` (used to log in to Linux EC2 instances)
  - **HTTP** – Port `80` (used to access applications over HTTP)
  - **HTTPS** – Port `443` (used to access applications securely)
- It is **not possible to explicitly DENY** a protocol in a Security Group.
  - To block traffic, you must **remove the allow rule**.
- Security Groups only support **ALLOW rules**, not DENY rules.
- AWS provides a **default Security Group** in every VPC.
- Security Groups support **three types of sources**:
  1. Anywhere (`0.0.0.0/0`)
  2. Custom (specific IP range or Security Group)
  3. My IP
- You can attach **multiple Security Groups to a single EC2 instance**.
- A single Security Group can be attached to **multiple EC2 instances**.
- A newly created Security Group:
  - Has **no inbound rules (all denied)**
  - Allows **all outbound traffic by default**
- Security Groups are **stateful**.
  - If inbound traffic is allowed, the corresponding outbound traffic is automatically allowed.

**Definitions**
- **Stateful**: If you allow traffic in inbound rules, you do **not** need to allow it in outbound rules.
- **Stateless**: If you allow traffic in inbound rules, you **must** allow it in outbound rules as well.

---

## NACL (Network Access Control List)

- A NACL provides an **additional layer of security** for EC2 instances.
- NACLs operate at the **subnet level**.
- Traffic flow order:
  - Request hits the **NACL first**, then the **Security Group**.
- Like Security Groups, NACLs have:
  - **Inbound rules**
  - **Outbound rules**
- Key differences:
  - **Security Group** → Instance level
  - **NACL** → Subnet level
- By default:
  - **Inbound rules are allowed**
  - **Outbound rules are allowed**
- NACLs support both **ALLOW and DENY** rules.
- NACLs are **stateless**.
  - You must explicitly allow traffic in **both inbound and outbound rules**.
- A single NACL can be associated with **multiple subnets**.
- A subnet can be associated with **only one NACL at a time**.
