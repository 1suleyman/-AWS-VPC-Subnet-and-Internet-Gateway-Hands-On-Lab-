# 🌐 My AWS VPC, Subnet, and Internet Gateway Hands-On Lab

Welcome to my **AWS Networking Hands-On Lab**! In this project, I’m learning how to create a **VPC**, configure **subnets**, and attach an **internet gateway** to connect my resources to the internet. This is a foundational skill for securely organizing and deploying resources in AWS.

**Part 1 in my networking series**

---

## 🛠️ Project Overview

### My Goals

1. Create a custom **VPC**.
2. Launch a **subnet** inside my VPC.
3. Attach an **internet gateway** so my resources can reach the internet.
4. Understand why VPCs, subnets, and IGWs matter, using practical analogies.

---

## 📚 Why This Matters to Me

* **VPC = My Private Cloud City** 🏙️
  Without a VPC, all my AWS resources would exist in one giant, public cloud space. Anyone could see or access them! A VPC gives me **privacy, control, and organization** over my cloud resources.

* **Subnet = Neighborhood** 🏘️
  Subnets are like neighborhoods in my cloud city. They help me separate **public-facing resources** (like web servers) from **private resources** (like databases).

* **Internet Gateway = Bridge to the World** 🌉
  An IGW is like a bridge connecting my city to the outside world. It allows resources in public subnets to access external networks and lets others access them too.

💡 *Analogy:* My VPC is a city, subnets are neighborhoods, and the internet gateway is my bridge connecting the city to the internet.

---

## 🏗️ Step 1: Creating My VPC

1. I opened the **AWS Management Console** and searched for `VPC`.
2. I went to **Your VPCs** in the left navigation pane.
3. I clicked **Create VPC** → **VPC Only**.
4. I configured my VPC:

| Setting         | Value        |
| --------------- | ------------ |
| Name tag        | Suleyman VPC |
| IPv4 CIDR block | 10.0.0.0/16  |

5. I clicked **Create VPC**.

<img width="227" height="35" alt="Screenshot 2025-09-17 at 10 46 00" src="https://github.com/user-attachments/assets/4f22fd86-15ae-4ee2-a9e9-377e0d9fe152" />

💡 **Tip for me:** The `/16` CIDR block gives me 65,536 IP addresses for my VPC.

---

## 🏘️ Step 2: Creating My Subnet

1. In the VPC Dashboard, I went to **Subnets**.
2. I clicked **Create Subnet**.
3. I configured my subnet:

| Setting                | Value        |
| ---------------------- | ------------ |
| VPC ID                 | Suleyman VPC |
| Subnet name            | Public 1     |
| Availability Zone      | eu-west-2a   |
| IPv4 subnet CIDR block | 10.0.0.0/24  |

4. I clicked **Create Subnet**.

<img width="293" height="43" alt="Screenshot 2025-09-17 at 10 49 04" src="https://github.com/user-attachments/assets/83962dae-29cb-4ab4-8a75-f19325cfa405" />

5. I selected **Public 1** → **Actions** → **Edit subnet settings** → checked **Enable auto-assign public IPv4 address** → **Save**.

<img width="354" height="55" alt="Screenshot 2025-09-17 at 10 49 41" src="https://github.com/user-attachments/assets/83b40a3e-682c-4a12-a9b3-6366f9224a65" />

💡 **Tip for me:** Enabling auto-assign public IPv4 gives my EC2 instances instant internet access.

---

## 🌉 Step 3: Attaching My Internet Gateway

1. In the VPC Dashboard, I went to **Internet Gateways**.
2. I clicked **Create internet gateway**, named it `Suleyman IG`, then clicked **Create internet gateway**.

<img width="352" height="54" alt="Screenshot 2025-09-17 at 10 51 57" src="https://github.com/user-attachments/assets/8eaf76ed-584b-4325-8efe-db449a98c734" />

3. I selected my new IGW → **Actions** → **Attach to VPC** → `Suleyman VPC` → **Attach internet gateway**.

<img width="190" height="35" alt="Screenshot 2025-09-17 at 10 52 51" src="https://github.com/user-attachments/assets/c6d31834-eba6-47b4-887e-8de8cb93a443" />

💡 **Tip for me:** Attaching an IGW lets resources in my public subnet communicate with the internet.

---

## ✅ What I’ve Achieved

* A **custom VPC** isolating my resources.
* A **public subnet** ready for internet-facing resources.
* An **internet gateway** connecting my VPC to the internet.

🎉 *I’ve built my own private city in the cloud with neighborhoods and a bridge to the outside world!*

---

## 🔮 My Next Steps

* Create **private subnets** for sensitive resources like databases.
* Launch **EC2 instances** in my public and private subnets.
* Learn about **routing tables** to control traffic flow inside my VPC.
* Explore **security groups and NACLs** for access control.

---

## 📖 Key Concepts I Learned

| Concept                | My Understanding                             |
| ---------------------- | -------------------------------------------- |
| VPC                    | My isolated private cloud network            |
| Subnet                 | A neighborhood inside my VPC                 |
| Public Subnet          | Accessible to the internet                   |
| Private Subnet         | Not accessible from the internet             |
| Internet Gateway (IGW) | Connects my VPC to the internet              |
| IPv4 CIDR Block        | IP address range for my network              |
| Availability Zone (AZ) | Physical cluster of data centers in a region |

---

## 📌 References I Used

* [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
* [AWS Subnets Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
* [AWS Internet Gateway Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)
