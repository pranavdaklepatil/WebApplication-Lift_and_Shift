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

This project demonstrates a **production-grade cloud migration** of the multi-tier VPROFILE web application to AWS using a **Lift & Shift strategy**. The workload is moved from on-premises/local infrastructure to AWS Cloud — improving scalability, availability, and cost-efficiency **without redesigning** the application architecture.

> 🔁 **Lift & Shift** = Same architecture, new home in the cloud.

---

## 🎯 Objectives

| Goal | Description |
|------|-------------|
| ☁️ Flexible Infra | Infrastructure that adapts to changing workloads automatically |
| 💰 No Upfront Cost | Leverage AWS's pay-as-you-go model |
| 🔄 Modernize Effectively | Transition from legacy environments to cloud infrastructure |
| 🏗️ IAAC Foundation | Lay the groundwork for automated infrastructure provisioning |

---

## 🏗️ Architecture Overview

```
Internet
    │
    ▼
┌─────────────────────┐
│   Application Load  │  ← HTTPS (ACM SSL Certificate)
│   Balancer (ALB)    │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Tomcat App Server  │  ← EC2 | vprofile-v2.war
│  (Ubuntu + Java)    │
└────────┬────────────┘
         │
    ┌────┴──────────────────┐
    │                       │
    ▼                       ▼
┌──────────┐        ┌───────────────┐
│  MySQL   │        │   Memcached   │
│  (db01)  │        │  (mc01)       │
└──────────┘        └───────────────┘
                    ┌───────────────┐
                    │   RabbitMQ    │
                    │  (rmq01)      │
                    └───────────────┘
         │
         ▼
┌─────────────────────┐
│     Amazon S3       │  ← Artifact Storage
└─────────────────────┘
```

---

## 🛠️ AWS Services Used

<table>
  <thead>
    <tr>
      <th>Service</th>
      <th>Icon</th>
      <th>Purpose</th>
      <th>Docs</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>EC2</strong></td>
      <td><img src="https://img.shields.io/badge/EC2-FF9900?logo=amazonec2&logoColor=white&style=flat-square"/></td>
      <td>Virtual Machines for Tomcat, RabbitMQ, Memcached, MySQL</td>
      <td><a href="https://docs.aws.amazon.com/ec2/">📄 EC2 Docs</a></td>
    </tr>
    <tr>
      <td><strong>ELB (ALB)</strong></td>
      <td><img src="https://img.shields.io/badge/ELB-FF9900?logo=amazonaws&logoColor=white&style=flat-square"/></td>
      <td>Distributes incoming HTTPS traffic across application targets</td>
      <td><a href="https://docs.aws.amazon.com/elasticloadbalancing/">📄 ELB Docs</a></td>
    </tr>
    <tr>
      <td><strong>Auto Scaling</strong></td>
      <td><img src="https://img.shields.io/badge/AutoScaling-FF9900?logo=amazonaws&logoColor=white&style=flat-square"/></td>
      <td>Automated VM scaling based on traffic demands</td>
      <td><a href="https://docs.aws.amazon.com/autoscaling/">📄 Auto Scaling Docs</a></td>
    </tr>
    <tr>
      <td><strong>S3</strong></td>
      <td><img src="https://img.shields.io/badge/S3-569A31?logo=amazons3&logoColor=white&style=flat-square"/></td>
      <td>Artifact storage for application WAR file</td>
      <td><a href="https://docs.aws.amazon.com/s3/">📄 S3 Docs</a></td>
    </tr>
    <tr>
      <td><strong>Route 53</strong></td>
      <td><img src="https://img.shields.io/badge/Route53-8C4FFF?logo=amazonroute53&logoColor=white&style=flat-square"/></td>
      <td>Private DNS — maps hostnames to private IPs (e.g., <code>db01.vprofile.in</code>)</td>
      <td><a href="https://docs.aws.amazon.com/route53/">📄 Route 53 Docs</a></td>
    </tr>
    <tr>
      <td><strong>IAM</strong></td>
      <td><img src="https://img.shields.io/badge/IAM-DD344C?logo=amazonaws&logoColor=white&style=flat-square"/></td>
      <td>User & Role management for S3 access</td>
      <td><a href="https://docs.aws.amazon.com/iam/">📄 IAM Docs</a></td>
    </tr>
    <tr>
      <td><strong>ACM</strong></td>
      <td><img src="https://img.shields.io/badge/ACM-FF9900?logo=amazonaws&logoColor=white&style=flat-square"/></td>
      <td>SSL/HTTPS certificates for secure communication</td>
      <td><a href="https://docs.aws.amazon.com/acm/">📄 ACM Docs</a></td>
    </tr>
  </tbody>
</table>

---

## ⚙️ Technology Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| App Server | <img src="https://img.shields.io/badge/Apache_Tomcat-F8DC75?logo=apachetomcat&logoColor=black&style=flat-square"/> Apache Tomcat | 10 |
| Database | <img src="https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white&style=flat-square"/> MySQL | Latest |
| Cache | <img src="https://img.shields.io/badge/Memcached-0099CC?logo=memcached&logoColor=white&style=flat-square"/> Memcached | Latest |
| Queue | <img src="https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white&style=flat-square"/> RabbitMQ | Latest |
| Build Tool | <img src="https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white&style=flat-square"/> Apache Maven | Latest |
| OS | <img src="https://img.shields.io/badge/Ubuntu-E95420?logo=ubuntu&logoColor=white&style=flat-square"/> Ubuntu | 22.04 LTS |

---

## 🔒 Security Groups

Three security groups are created to enforce a **layered security model** (defense in depth):

### 1️⃣ Load Balancer Security Group (`vprofile-ELB-SG`)
Allows inbound traffic only from the **public internet**:

| Type | Protocol | Port | Source |
|------|----------|------|--------|
| HTTP | TCP | 80 | `0.0.0.0/0` |
| HTTPS | TCP | 443 | `0.0.0.0/0` |

> 📄 [Security Groups Docs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)

---

### 2️⃣ Tomcat App Server Security Group (`vprofile-app-SG`)
Allows inbound traffic only from the **Load Balancer SG**:

| Type | Protocol | Port | Source |
|------|----------|------|--------|
| Custom TCP | TCP | 8080 | `vprofile-ELB-SG` |
| SSH | TCP | 22 | Your IP |

---

### 3️⃣ Backend Services Security Group (`vprofile-backend-SG`)
Allows inbound traffic only from the **App Server SG**:

| Service | Protocol | Port | Source |
|---------|----------|------|--------|
| MySQL | TCP | 3306 | `vprofile-app-SG` |
| Memcached | TCP | 11211 | `vprofile-app-SG` |
| RabbitMQ | TCP | 5672 | `vprofile-app-SG` |
| All Traffic (internal) | All | All | `vprofile-backend-SG` (self) |

---

## 🚀 Flow of Execution

### Step 1 — Create Key Pair

```bash
# AWS Console → EC2 → Key Pairs → Create Key Pair
Name: vprofile-prod-key
Type: RSA
Format: .pem
```

> 📄 [EC2 Key Pairs Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)

---

### Step 2 — Create Security Groups

Create the three security groups described in the [Security Groups](#-security-groups) section above via:
**AWS Console → EC2 → Security Groups → Create Security Group**

---

### Step 3 — Launch EC2 Instances

Launch instances with the correct security groups and user data provisioning scripts:

| Instance | OS | Security Group | Provisioning |
|----------|----|----------------|-------------|
| `app01` (Tomcat) | Ubuntu 22.04 | `vprofile-app-SG` | `tomcat_ubuntu.sh` |
| `db01` (MySQL) | CentOS / RHEL | `vprofile-backend-SG` | `mysql.sh` |
| `mc01` (Memcached) | CentOS / RHEL | `vprofile-backend-SG` | `memcache.sh` |
| `rmq01` (RabbitMQ) | CentOS / RHEL | `vprofile-backend-SG` | `rabbitmq.sh` |

> 📄 [EC2 Launch Instances Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html)

---

### Step 4 — Route 53 Private Hosted Zone

Create a **private hosted zone** and DNS records mapping hostnames to Private IPs:

```
Hosted Zone: vprofile.in  (Private)

db01.vprofile.in   →  <Private IP of db01>
mc01.vprofile.in   →  <Private IP of mc01>
rmq01.vprofile.in  →  <Private IP of rmq01>
```

> 📄 [Route 53 Private Hosted Zones Docs](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html)

---

### Step 5 — IAM Configuration

#### 5a. Create IAM User with S3 Full Access

```
AWS Console → IAM → Users → Create User
Name: vprofile-s3-user
Permissions: AmazonS3FullAccess
→ Create Access Key (for CLI use)
```

#### 5b. Create IAM Role for EC2 → S3 Access

```
AWS Console → IAM → Roles → Create Role
Trusted Entity: EC2
Permissions: AmazonS3FullAccess
Name: vprofile-ec2-s3-role
→ Attach role to app01 instance
```

> 📄 [IAM Roles Docs](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)

---

### Step 6 — Build the Artifact

Build the application locally using Maven:

```bash
# In your project root (VSCode terminal)
mvn install
```

The artifact is generated at:
```
target/vprofile-v2.war
```

> 📄 [Apache Maven Docs](https://maven.apache.org/guides/getting-started/)

---

### Step 7 — Upload Artifact to S3

Configure AWS CLI and upload the WAR file:

```bash
# Configure AWS CLI
aws configure

# Upload artifact to S3 bucket
aws s3 cp target/vprofile-v2.war s3://liftandshifts3/
```

> 📄 [AWS S3 CLI Docs](https://docs.aws.amazon.com/cli/latest/reference/s3/)

---

### Step 8 — Deploy Artifact on App Server

SSH into the app server and deploy:

```bash
# SSH into app server
ssh -i vprofile-prod-key.pem ubuntu@<app01-public-ip>

# Switch to root
sudo -i

# Download artifact from S3
aws s3 cp s3://liftandshifts3/vprofile-v2.war /tmp/

# Stop Tomcat service
systemctl stop tomcat10.service
systemctl daemon-reload

# Remove existing deployment
rm -rf /var/lib/tomcat10/webapps/ROOT

# Deploy new artifact
mkdir -p /var/lib/tomcat10/webapps
cp -f /tmp/vprofile-v2.war /var/lib/tomcat10/webapps/ROOT.war

# Start Tomcat service
systemctl start tomcat10.service

# Verify deployment
ls /var/lib/tomcat10/webapps
# → ROOT.war  ROOT/
```

> 📄 [Apache Tomcat Deployment Docs](https://tomcat.apache.org/tomcat-10.1-doc/deployer-howto.html)

---

### Step 9 — Create Target Group & Load Balancer

#### 9a. Create Target Group

```
AWS Console → EC2 → Target Groups → Create Target Group
Type: Instances
Protocol: HTTP
Port: 8080
Health Check Path: /login
→ Register app01 instance
```

#### 9b. Create Application Load Balancer

```
AWS Console → EC2 → Load Balancers → Create ALB
Name: vprofile-prod-elb
Scheme: Internet-facing
Security Group: vprofile-ELB-SG
Listener: HTTPS 443 → Forward to Target Group
Certificate: (from ACM)
```

> 📄 [Application Load Balancer Docs](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

---

### Step 10 — Map Domain & Verify

```
Your DNS Provider (e.g., GoDaddy / Route 53 Public):
vprofile.yourdomain.com  →  CNAME  →  <ALB DNS Name>
```

Then verify by opening `https://vprofile.yourdomain.com` in your browser.

---

## 📁 Project Structure

```
Project_LiftAndShift/
├── src/                        # Application source code
├── target/
│   └── vprofile-v2.war         # Built artifact
├── userdata/
│   ├── mysql.sh                # MySQL provisioning script
│   ├── memcache.sh             # Memcached provisioning script
│   ├── rabbitmq.sh             # RabbitMQ provisioning script
│   └── tomcat_ubuntu.sh        # Tomcat provisioning script
├── pom.xml                     # Maven build configuration
└── README.md
```

---

## ✅ Prerequisites

Before you begin, ensure you have:

- [x] An active **AWS Account** — [Create one here](https://aws.amazon.com/free/)
- [x] **AWS CLI** installed and configured — [Install Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- [x] **Java JDK 11+** installed — [Download](https://adoptium.net/)
- [x] **Apache Maven** installed — [Install Guide](https://maven.apache.org/install.html)
- [x] **Git** installed — [Download](https://git-scm.com/downloads)
- [x] Basic knowledge of AWS Console navigation

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

[![AWS](https://img.shields.io/badge/Powered_by-AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)

</div>