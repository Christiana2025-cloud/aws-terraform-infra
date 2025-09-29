# aws-terraform-infra
Infrastructure for a scalable web application on AWS using Terraform


This project provisions a scalable and secure AWS infrastructure using **Terraform**.  
It demonstrates infrastructure as code (IaC) best practices, modular design, and deployment of AWS services for hosting a simple web application.

---

## 🚀 Project Overview
The infrastructure includes:
- **VPC** with public and private subnets across multiple Availability Zones  
- **Internet Gateway** and **NAT Gateway** for internet access  
- **Security Groups** and **Network ACLs** for traffic control  
- **Auto Scaling Group** with EC2 instances  
- **Application Load Balancer (ALB)** for distributing traffic  
- **RDS (MySQL/Postgres)** database in private subnets  
- **S3 bucket** for static asset hosting or website content  
- **CloudWatch Alarms** for monitoring  

---

## 🏗️ Architecture
Below is the high-level architecture diagram of the infrastructure:  

![Architecture Diagram](./architecture.png)  
*(Replace with your actual diagram — e.g., draw with [Lucidchart](https://lucidchart.com), [Draw.io](https://app.diagrams.net/), or [Excalidraw](https://excalidraw.com/))*

---

## 📂 Project Structure
.
├── main.tf # Root module, orchestrates resources
├── providers.tf # AWS provider configuration
├── variables.tf # Input variables
├── outputs.tf # Output values
├── vpc.tf # Networking resources (VPC, subnets, route tables, etc.)
├── ec2.tf # EC2, Launch Template, Auto Scaling Group
├── rds.tf # Database resources
├── s3.tf # S3 bucket for static assets
├── cloudwatch.tf # Monitoring and alarms
└── .gitignore # Ignore Terraform state/secrets

yaml
Copy code

---

## ⚙️ Prerequisites
- AWS Account with programmatic access (IAM user or role)  
- Terraform installed locally → [Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)  
- AWS CLI configured with credentials (`aws configure`)  

---

## 🔧 Usage

**Clone the repository**
  
Initialize Terraform

bash
Copy code
terraform init

Preview the infrastructure plan

bash
Copy code
terraform plan

Apply the configuration

bash
Copy code
terraform apply

Destroy the infrastructure (when done)

bash
Copy code
terraform destroy

📊 Outputs
After terraform apply, I obtained:

ALB DNS Name (access the web app)

RDS Endpoint

S3 bucket name

💡 Lessons Learned
Writing modular and reusable Terraform code

Managing AWS resources with IaC

Debugging Terraform errors and handling state files

Best practices in cloud security (private subnets, IAM roles, etc.)

📌 Next Steps
Add CI/CD pipeline (e.g., GitHub Actions) to automate Terraform deployment

Implement HTTPS using ACM certificates with the ALB

Add a CloudFront distribution in front of S3/ALB for caching
