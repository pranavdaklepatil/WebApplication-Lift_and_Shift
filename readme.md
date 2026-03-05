# AWS Lift & Shift: Multi-Tier Web Application (VPROFILE)

## 📌 About The Project
This project demonstrates the migration of a multi-tier web application stack (VPROFILE) to the AWS Cloud for production. It utilizes a **Lift & Shift strategy**, moving the workload to a cloud environment to improve scalability, manageability, and cost-efficiency without redesigning the application architecture.

http://googleusercontent.com/image_generation_content/0

---

## 🎯 Objective
* **Flexible Infra:** Create an infrastructure that adapts to changing workloads.
* **No Upfront Cost:** Leverage AWS's pay-as-you-go model.
* **Modernize Effectively:** Transition from legacy environments to modern cloud infrastructure.
* **IAAC (Infrastructure as Code):** Lay the groundwork for automated infrastructure provisioning.

---

## 💡 Solution: Cloud Setup
By shifting to AWS, this project achieves a robust cloud setup characterized by:
* **IAAS (Infrastructure as a Service):** Utilizing core AWS compute and networking resources.
* **Automation:** Streamlining deployments and scaling.
* **PayAsUGo:** Optimizing costs by paying only for what is used.
* **Flexibility & Ease of Infra Management:** Simplifying operations and maintenance.

---

## 🛠️ AWS Services Used
* **EC2 Instances:** Virtual Machines hosting Tomcat, RabbitMQ, Memcached, and MySQL.
* **ELB (Elastic Load Balancer):** Replaces traditional Nginx load balancing to distribute incoming application traffic across multiple targets.
* **Auto Scaling:** Provides automation for VM scaling based on traffic demands.
* **S3 / EFS Storage:** Provides reliable and highly available shared storage.
* **Route 53:** Serves as the Private DNS service to manage internal domain name routing (e.g., `db01 => IP`).
* **Amazon Certificate Manager (ACM):** Manages SSL/HTTPS certificates for secure communication.

---

## 🚀 Flow of Execution

1. **Login to AWS Account:** Access the AWS Management Console.
2. **Create Key Pairs:** Secure access credentials for EC2 instances.
3. **Create Security Groups:** Define firewall rules for the Load Balancer, Tomcat application tier, and backend services (MySQL, Memcached, RabbitMQ).
4. **Launch Instances with User Data:** Provision EC2 instances using Bash scripts for automated bootstrapping.
5. **Update IP to Name Mapping:** Configure Route 53 private hosted zones.
6. **Build Application:** Compile the application from the source code.
7. **Upload to S3 Bucket:** Store the built artifacts safely.
8. **Download Artifact:** Pull the application artifact from S3 to the Tomcat EC2 Instance.
9. **Setup ELB with HTTPS:** Configure the Application Load Balancer with an SSL certificate from Amazon Certificate Manager.
10. **Map ELB Endpoint:** Map the Load Balancer endpoint to your website's public domain name in your DNS provider (e.g., GoDaddy).
11. **Verify:** Test the application endpoint to ensure successful deployment and functionality.