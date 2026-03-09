<div align="center">

<img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="AWS Logo" width="120"/>

# 🚀 Project Lift & Shift — AWS Cloud Migration
### Multi-Tier Web Application (VPROFILE) on AWS

[![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)
[![EC2](https://img.shields.io/badge/EC2-Compute-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)](https://aws.amazon.com/ec2/)
[![Java](https://img.shields.io/badge/Java-Maven-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://maven.apache.org/)
[![Tomcat](https://img.shields.io/badge/Apache-Tomcat-F8DC75?style=for-the-badge&logo=apachetomcat&logoColor=black)](https://tomcat.apache.org/)
[![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![RabbitMQ](https://img.shields.io/badge/RabbitMQ-Messaging-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)](https://www.rabbitmq.com/)
[![Memcached](https://img.shields.io/badge/Memcached-Cache-0099CC?style=for-the-badge&logo=memcached&logoColor=white)](https://memcached.org/)

</div>

---

## 📌 About The Project

This project demonstrates a **production-grade cloud migration** of the multi-tier **VPROFILE** web application to AWS using a **Lift & Shift strategy**. The workload is moved from on-premises infrastructure to AWS Cloud — improving scalability, availability, and cost-efficiency **without redesigning** the application architecture.

The application is a Java-based social networking platform built with Spring MVC, Spring Security, and Spring Data JPA, using MySQL for persistence, Memcached for session caching, RabbitMQ for messaging, and Tomcat as the servlet container.

> 🔁 **Lift & Shift** = Same architecture, new home in the cloud.

---

## 🎯 Objectives

<div align="center">

| Goal | Description |
|:----:|:-----------|
| ☁️ **Flexible Infra** | Infrastructure that adapts to changing workloads automatically |
| 💰 **No Upfront Cost** | Leverage AWS's pay-as-you-go model |
| 🔄 **Modernize Effectively** | Transition from legacy environments to cloud infrastructure |
| 🏗️ **IAAC Foundation** | Lay the groundwork for automated infrastructure provisioning |

</div>

---

## 🏗️ Architecture Overview

<div align="center">

> Complete cloud architecture — GoDaddy DNS → ALB → Tomcat App Server → Backend Services (MySQL, Memcached, RabbitMQ), with Route 53 private DNS and S3 for artifact storage.

![Architecture Diagram](screenshorts/Architecture.png)

</div>

---

## 🛠️ AWS Services Used

<div align="center">

| Service | Icon | Purpose |
|:-------:|:----:|:--------|
| **EC2** | ![](https://img.shields.io/badge/EC2-FF9900?logo=amazonec2&logoColor=white&style=flat-square) | Virtual Machines for Tomcat, RabbitMQ, Memcached, MySQL |
| **ELB (ALB)** | ![](https://img.shields.io/badge/ELB-FF9900?logo=amazonaws&logoColor=white&style=flat-square) | Distributes incoming HTTP/HTTPS traffic across app targets |
| **Auto Scaling** | ![](https://img.shields.io/badge/AutoScaling-FF9900?logo=amazonaws&logoColor=white&style=flat-square) | Automated VM scaling based on traffic demands |
| **S3** | ![](https://img.shields.io/badge/S3-569A31?logo=amazons3&logoColor=white&style=flat-square) | Artifact storage for the application WAR file |
| **Route 53** | ![](https://img.shields.io/badge/Route53-8C4FFF?logo=amazonroute53&logoColor=white&style=flat-square) | Private DNS — maps hostnames to private IPs |
| **IAM** | ![](https://img.shields.io/badge/IAM-DD344C?logo=amazonaws&logoColor=white&style=flat-square) | User & Role management for secure S3 access |
| **ACM** | ![](https://img.shields.io/badge/ACM-FF9900?logo=amazonaws&logoColor=white&style=flat-square) | SSL/HTTPS certificates for secure communication |

</div>

---

## ⚙️ Technology Stack

<div align="center">

| Layer | Technology | Version |
|:-----:|:----------:|:-------:|
| App Server | ![](https://img.shields.io/badge/Apache_Tomcat-F8DC75?logo=apachetomcat&logoColor=black&style=flat-square) Apache Tomcat | 10 |
| Database | ![](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white&style=flat-square) MySQL | 8 |
| Cache | ![](https://img.shields.io/badge/Memcached-0099CC?logo=memcached&logoColor=white&style=flat-square) Memcached | Latest |
| Message Broker | ![](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white&style=flat-square) RabbitMQ | Latest |
| Build Tool | ![](https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white&style=flat-square) Apache Maven | 3 |
| OS (App Server) | ![](https://img.shields.io/badge/Ubuntu-E95420?logo=ubuntu&logoColor=white&style=flat-square) Ubuntu | 22.04 LTS |
| OS (Backend) | ![](https://img.shields.io/badge/Amazon_Linux-FF9900?logo=amazonaws&logoColor=white&style=flat-square) Amazon Linux | 2023 |

</div>

---

## ✅ Prerequisites

### 🔧 Local Build Requirements

<div align="center">

| Tool | Version | Download |
|:----:|:-------:|:--------:|
| ![](https://img.shields.io/badge/JDK-ED8B00?logo=openjdk&logoColor=white&style=flat-square) **Java JDK** | 11 | [📥 Eclipse Temurin JDK 11](https://adoptium.net/temurin/releases/?version=11) |
| ![](https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white&style=flat-square) **Apache Maven** | 3.x | [📥 Maven Download](https://maven.apache.org/download.cgi) |
| ![](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white&style=flat-square) **MySQL** | 8.x | [📥 MySQL Community Server](https://dev.mysql.com/downloads/mysql/) |

</div>

### ☁️ AWS & DevOps Requirements

- [x] An active **AWS Account** 
- [x] **AWS CLI v2** installed and configured — [📄 Install Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- [x] **Git** installed — [📥 Download](https://git-scm.com/downloads)
- [x] Basic knowledge of AWS Console navigation

---

## 🧰 Technologies Used

### Application Framework

<div align="center">

| Technology | Badge |
|:----------:|:-----:|
| **Spring MVC** | ![](https://img.shields.io/badge/Spring_MVC-6DB33F?logo=spring&logoColor=white&style=flat-square) |
| **Spring Security** | ![](https://img.shields.io/badge/Spring_Security-6DB33F?logo=springsecurity&logoColor=white&style=flat-square) |
| **Spring Data JPA** | ![](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?logo=spring&logoColor=white&style=flat-square) |
| **Maven** | ![](https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white&style=flat-square) |
| **JSP** | ![](https://img.shields.io/badge/JSP-Jakarta-007396?logo=jakarta&logoColor=white&style=flat-square) |

</div>

### Infrastructure & Services

<div align="center">

| Technology | Badge |
|:----------:|:-----:|
| **Apache Tomcat** | ![](https://img.shields.io/badge/Tomcat-10-F8DC75?logo=apachetomcat&logoColor=black&style=flat-square) |
| **MySQL** | ![](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql&logoColor=white&style=flat-square) |
| **Memcached** | ![](https://img.shields.io/badge/Memcached-0099CC?logo=memcached&logoColor=white&style=flat-square) |
| **RabbitMQ** | ![](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white&style=flat-square) |
| **ElasticSearch** | ![](https://img.shields.io/badge/Elasticsearch-005571?logo=elasticsearch&logoColor=white&style=flat-square) |

</div>

---

## 🗄️ Database Setup

This project uses **MySQL 8** as the primary relational database. The application connects to the `accounts` schema which stores user profiles, contacts, and related data.

### DB Dump File Location

```
src/main/resources/db_backup.sql
```

> The `db_backup.sql` file is a **MySQL dump** containing the full schema and seed data for the `accounts` database.

### Import the Database

```bash
# Quick import
mysql -u <user_name> -p accounts < db_backup.sql
```

**Step-by-step:**

```bash
# 1. Log into MySQL
mysql -u root -p

# 2. Create the database
CREATE DATABASE accounts;
EXIT;

# 3. Import the dump
mysql -u root -p accounts < src/main/resources/db_backup.sql
```

> The EC2 provisioning script (`mysql.sh`) handles this automatically on the cloud instance at first boot by cloning the repo and running the dump restore.

---

## 🔒 Security Groups

Three security groups enforce a **layered security model** (defense in depth). Each tier only allows traffic from the tier directly above it.

### 1️⃣ Load Balancer Security Group — `LiftAndShift-ELB-SG`

Allows inbound traffic from the **public internet** only:

<div align="center">

| Type | Protocol | Port | Source |
|:----:|:--------:|:----:|:------:|
| HTTP | TCP | 80 | `0.0.0.0/0` , `::/0` |
| HTTPS | TCP | 443 | `0.0.0.0/0` , `::/0` |

![ELB SG — Inbound Rules](screenshorts/LiftAndShift-ELB-SG.png)

![ELB SG — Creation View](screenshorts/SecurityGroupForELB.png)

</div>

---

### 2️⃣ Tomcat App Server Security Group — `LiftAndShift-App-Server-SG`

Allows inbound traffic only from the **ELB Security Group** on port 8080:

<div align="center">

| Type | Protocol | Port | Source |
|:----:|:--------:|:----:|:------:|
| Custom TCP | TCP | 8080 | `LiftAndShift-ELB-SG` |
| SSH | TCP | 22 | My IP |

![App Server SG — Creation View](screenshorts/Screenshot_2026-03-05_113836.png)

</div>

---

### 3️⃣ Backend Services Security Group — `LiftAndShift-Backend-Server-SG`

Allows inbound traffic only from the **App Server SG**, plus a self-referencing rule for inter-service communication:

<div align="center">

| Service | Protocol | Port | Source |
|:-------:|:--------:|:----:|:------:|
| MySQL/Aurora | TCP | 3306 | `LiftAndShift-App-Server-SG` |
| Memcached | TCP | 11211 | `LiftAndShift-App-Server-SG` |
| RabbitMQ | TCP | 5672 | `LiftAndShift-App-Server-SG` |
| SSH | TCP | 22 | My IP |
| All Traffic (internal) | All | All | `LiftAndShift-Backend-Server-SG` *(self)* |

</div>

> ⚠️ The **self-referencing rule** must be added **after** the SG is first created — it allows MySQL, Memcached, and RabbitMQ to communicate with each other within the same security group.

<div align="center">

![Backend Server SG — Initial Creation](screenshorts/LiftAndShift-Backend-Server-SG.png)

![Backend Server SG — Edit Inbound Rules](screenshorts/Edit-LiftAndShift-Backend-Server-SG.png)

![Backend Server SG — Self-Reference Rule Added](screenshorts/Edit-LiftAndShift-Backend-Server-mysql-db01-2.png)

</div>

---

## 🚀 Flow of Execution

### Step 1 — Create Key Pair

```bash
# AWS Console → EC2 → Key Pairs → Create Key Pair
Name   : vprofile-prod-key
Type   : RSA
Format : .pem
```

> 📄 [EC2 Key Pairs Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)

---

### Step 2 — Create Security Groups

Create the three security groups described in the [Security Groups](#-security-groups) section above:

**AWS Console → EC2 → Security Groups → Create Security Group**

Refer to the screenshots in the Security Groups section for the exact inbound rule configuration for each SG.

---

### Step 3 — Launch EC2 Instances with User Data

Launch instances with the correct AMI, security group, and **User Data** script for automated bootstrapping at first boot:

<div align="center">

| Instance Name | AMI | Instance Type | Security Group | User Data |
|:-------------:|:---:|:-------------:|:--------------:|:---------:|
| `LiftAndShift-app01` | Ubuntu 22.04 | t3.micro | `LiftAndShift-App-Server-SG` | `tomcat_ubuntu.sh` |
| `LiftAndShift-db01` | Amazon Linux 2023 | t3.micro | `LiftAndShift-Backend-Server-SG` | `mysql.sh` |
| `LiftAndShift-mc01` | Amazon Linux 2023 | t3.micro | `LiftAndShift-Backend-Server-SG` | `memcache.sh` |
| `LiftAndShift-rmq01` | Amazon Linux 2023 | t3.micro | `LiftAndShift-Backend-Server-SG` | `rabbitmq.sh` |

</div>

> The `mysql.sh` user data script installs MariaDB 105, clones the application repo from GitHub, sets the root password, and auto-restores the `db_backup.sql` dump on first boot — fully automated, zero manual DB setup needed.

<div align="center">

![EC2 — db01 Launch with mysql.sh User Data](screenshorts/Edit-LiftAndShift-Backend-Server-mysql-db01-2.png)

![EC2 — All 4 Instances Running](screenshorts/Instances_.png)

</div>

> 📄 [EC2 Launch Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) · [EC2 User Data](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html)

---

### Step 4 — Route 53 Private Hosted Zone

Create a **private hosted zone** scoped to your VPC, then add `A` records mapping each backend hostname to its **Private IP**:

```
Hosted Zone : LiftAandShift.in   (Type: Private — VPC: vpc-0b9cc79a93a97db82)

db01.LiftAandShift.in   →  172.31.68.80    (LiftAndShift-db01  Private IP)
mc01.LiftAandShift.in   →  172.31.78.35    (LiftAndShift-mc01  Private IP)
rmq01.LiftAandShift.in  →  172.31.79.144   (LiftAndShift-rmq01 Private IP)
```

> These DNS names are referenced in `application.properties` of the Spring app so the Tomcat server resolves backend services by hostname — no hardcoded IPs, no reconfiguration needed if IPs change.

<div align="center">

![Route 53 — Create Private Hosted Zone](screenshorts/HostedZone.png)

</div>

> 📄 [Route 53 Private Hosted Zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html)

---

### Step 5 — IAM Configuration

#### 5a. Create IAM User — S3 Artifact Upload

Create a programmatic IAM user for local CLI artifact uploads from your dev machine:

```
AWS Console → IAM → Users → Create User
Name        : LiftAndShift-Admin
Permissions : AmazonS3FullAccess
→ Security Credentials → Create Access Key → CLI use case → Download CSV
```

<div align="center">

![IAM — Create User LiftAndShift-Admin](screenshorts/IAM_User_.png)

</div>

#### 5b. Create IAM Role — EC2 → S3 Pull

Attach a role to the app server so it can pull the artifact from S3 **without needing any static credentials**:

```
AWS Console → IAM → Roles → Create Role
Trusted Entity : AWS Service → EC2
Permissions    : AmazonS3FullAccess
Role Name      : vprofile-ec2-s3-role
→ EC2 → Instances → Select app01 → Actions → Security → Modify IAM Role → Attach
```

> 📄 [IAM Roles for EC2](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html)

---

### Step 6 — Build the Artifact

Clone the repo and build the application locally using Maven:

```bash
# Clone the repository
git clone https://github.com/pranavdaklepatil/WebApplication-Lift_and_Shift.git
cd WebApplication-Lift_and_Shift

# Build with Maven
mvn install
```

The WAR artifact is generated at:

```
target/vprofile-v2.war
```

<div align="center">

![Maven — mvn install Build Output](screenshorts/Screenshot_2026-03-05_121844.png)

</div>

> 📄 [Apache Maven Build Guide](https://maven.apache.org/guides/getting-started/)

---

### Step 7 — Create S3 Bucket & Upload Artifact

#### 7a. Create the S3 Bucket

```
AWS Console → S3 → Create Bucket
Bucket Name      : LiftAndShift-Bucket
Region           : US East (N. Virginia) us-east-1
Bucket Type      : General Purpose
Object Ownership : ACLs disabled (recommended)
Block Public Access: Enabled
```

<div align="center">

![S3 — Create Bucket](screenshorts/S3_Bucket_.png)

</div>

#### 7b. Configure AWS CLI & Upload

```bash
# Configure AWS CLI with LiftAndShift-Admin credentials
aws configure
# AWS Access Key ID     : <from CSV>
# AWS Secret Access Key : <from CSV>
# Default region        : us-east-1
# Default output format : json

# Upload the built artifact
aws s3 cp target/vprofile-v2.war s3://liftandshifts3/
```

> 📄 [AWS S3 CLI Reference](https://docs.aws.amazon.com/cli/latest/reference/s3/)

---

### Step 8 — Deploy Artifact on App Server

SSH into the app server. The attached IAM Role grants the instance permission to pull from S3 — no credentials needed:

```bash
# SSH into app server
ssh -i vprofile-prod-key.pem ubuntu@<app01-public-ip>

# Switch to root
sudo -i

# Pull artifact from S3 via IAM Role (no keys needed)
aws s3 cp s3://liftandshifts3/vprofile-v2.war /tmp/

# Stop Tomcat and reload daemon
systemctl stop tomcat10.service
systemctl daemon-reload

# Remove old ROOT deployment
rm -rf /var/lib/tomcat10/webapps/ROOT

# Deploy new WAR as ROOT application
mkdir -p /var/lib/tomcat10/webapps
cp -f /tmp/vprofile-v2.war /var/lib/tomcat10/webapps/ROOT.war

# Start Tomcat (will auto-unpack ROOT.war → ROOT/)
systemctl start tomcat10.service

# Verify
ls /var/lib/tomcat10/webapps
# Expected: ROOT.war  ROOT/
```

> 📄 [Apache Tomcat Deployment Docs](https://tomcat.apache.org/tomcat-10.1-doc/deployer-howto.html)

---

### Step 9 — Create Target Group

Create a target group pointing to the Tomcat app server on port 8080:

```
AWS Console → EC2 → Target Groups → Create Target Group
Target Type         : Instances
Name                : LiftAndShift-TG
Protocol            : HTTP
Port                : 8080
IP Address Type     : IPv4
VPC                 : vpc-0b9cc79a93a97db82
Health Check Path   : /
Health Check Port   : Override → 8080
Healthy Threshold   : 5
Unhealthy Threshold : 2
Timeout             : 5 seconds
→ Register Target   : LiftAndShift-app01 on port 8080
```

<div align="center">

![Target Group — Create & Settings](screenshorts/TG-1.png)

![Target Group — Health Check Configuration](screenshorts/TG-2.png)

![Target Group — Register app01 as Target](screenshorts/TG-3.png)

</div>

> 📄 [Target Groups for ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)

---

### Step 10 — Create Application Load Balancer

#### 10a. Basic Configuration

```
Name   : LiftAndShift-ELB
Scheme : Internet-facing
Type   : Application Load Balancer
IP Type: IPv4
```

<div align="center">

![ALB — Basic Configuration](screenshorts/ELB-1.png)

</div>

#### 10b. Network Mapping

```
VPC : vpc-0b9cc79a93a97db82 (default)
Availability Zones (select all):
  ✅ us-east-1a  ✅ us-east-1b  ✅ us-east-1c
  ✅ us-east-1d  ✅ us-east-1e  ✅ us-east-1f
```

<div align="center">

![ALB — Network Mapping & AZ Selection](screenshorts/ELB-2.png)

</div>

#### 10c. Security Group & Listener

```
Security Group : LiftAndShift-ELB-SG
Listener       : HTTP:80 → Forward to LiftAndShift-TG (Weight: 1)
```

<div align="center">

![ALB — Security Group & Listener Routing](screenshorts/ELB-3.png)

</div>

#### 10d. Load Balancer — Active

After creation, the ALB shows **Active** status across 6 Availability Zones with DNS auto-assigned:

<div align="center">

![ALB — Active & Running](screenshorts/ELB-4.png)

</div>

> 📄 [Application Load Balancer Docs](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

---

### Step 11 — Map Domain & Verify

Map your custom domain to the ALB DNS name via your DNS provider (e.g., GoDaddy):

```
Type  : CNAME
Host  : vprofile  (or @)
Value : LiftAndShift-ELB-<id>.us-east-1.elb.amazonaws.com
TTL   : 600
```

Open the ELB DNS endpoint in your browser to confirm the VPROFILE app is live and accessible:

<div align="center">

![Application Live — VPROFILE Login Page via ELB](screenshorts/ELB-5-working_.png)

</div>

> ✅ **Deployment successful!** The VPROFILE login page is live and served through the AWS Application Load Balancer.

---

## 📁 Project Structure

```
WebApplication-Lift_and_Shift/
├── src/
│   └── main/
│       ├── java/                       # Spring MVC / Security / JPA source code
│       ├── webapp/
│       │   └── WEB-INF/
│       │       └── views/              # JSP view templates
│       └── resources/
│           ├── application.properties  # DB, cache, MQ connection config
│           └── db_backup.sql           # MySQL schema + seed data dump
├── target/
│   └── vprofile-v2.war                 # Built artifact (mvn install output)
├── userdata/
│   ├── mysql.sh                        # MariaDB install + DB restore script
│   ├── memcache.sh                     # Memcached install script
│   ├── rabbitmq.sh                     # RabbitMQ install script
│   └── tomcat_ubuntu.sh                # Tomcat 10 install script (Ubuntu)
├── screenshorts/                       # All project screenshots
├── pom.xml                             # Maven project configuration
└── README.md
```

---

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

Made with ❤️ | AWS Cloud Migration Project

</div>