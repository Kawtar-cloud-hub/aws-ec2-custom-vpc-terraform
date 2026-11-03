# Deploying Highly Available EC2 Instances in a Custom AWS VPC with Terraform

This project demonstrates how to provision a secure, multi-tier cloud infrastructure on Amazon Web Services (AWS) using **Terraform**. It builds a custom Virtual Private Cloud (VPC) with segregated subnets and deploys compute resources across public and private tiers.

## 🏗️ Architecture Overview

* **Custom VPC:** A dedicated VPC (`10.0.0.0/16`) with DNS support enabled.
* **Public Subnet (`10.0.1.0/24`):** Hosts a public-facing EC2 instance (acting as a web server or Bastion host) with an automatic public IP assigned.
* **Private Subnet (`10.0.2.0/24`):** Hosts a private backend EC2 instance isolated from direct internet access.
* **Security Group (`web-server-sg`):** Acts as a stateful virtual firewall allowing inbound HTTP (Port 80) and SSH (Port 22) traffic.

---

## 📁 Project Structure

```text
aws-ec2-custom-vpc-terraform/
├── providers.tf     # AWS provider and version configurations
├── main.tf          # VPC and Subnet resource definitions
├── security.tf      # Security groups and firewall rules
├── ec2.tf           # Public and Private EC2 instance definitions
└── .gitignore       # Files to ignore (Terraform state, local files)
🚀 Prerequisites
Before running the configuration, ensure you have:

An active AWS Account with administrative permissions.

Terraform (v1.0+) installed on your local machine.

AWS CLI configured with your credentials (aws configure).

⚙️ Deployment Steps
Clone the repository:
git clone [https://github.com/Your-Username/aws-ec2-custom-vpc-terraform.git](https://github.com/Your-Username/aws-ec2-custom-vpc-terraform.git)
cd aws-ec2-custom-vpc-terraform
terraform init
terraform plan
terraform apply
(Type yes when prompted to confirm the resource creation).
