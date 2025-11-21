# AWS GuardDuty Automation with Terraform

![Portfolio Badge](https://img.shields.io/badge/Portfolio-Ready-brightgreen)

Automated Security Threat Detection | Infrastructure-as-Code | CI/CD Pipeline

This project demonstrates CloudOps security automation skills by deploying AWS GuardDuty using Terraform. It includes a complete CI/CD pipeline and visual documentation for portfolio purposes.

---

## 🎯 What This Project Does

- Automates AWS GuardDuty deployment across AWS accounts using Terraform  
- Enables real-time security findings notifications  
- Provides repeatable, auditable Infrastructure-as-Code deployment  
- Uses GitHub Actions for CI/CD automation  
- Includes step-by-step visual walkthroughs with screenshots and GIFs  

---

## 🔑 Key Features

### Infrastructure as Code
- Terraform automates the entire GuardDuty setup  
- Version-controlled configuration files (`main.tf`, `variables.tf`, `outputs.tf`)  
- Repeatable deployments across multiple AWS accounts  
- Auditable infrastructure changes  

### Security Monitoring
- GuardDuty enabled for threat detection (compromised credentials, crypto mining, unauthorized access)  
- Real-time detection of security threats  
- Extensible for SNS notifications, Lambda integrations, or custom monitoring rules  

### CI/CD Pipeline
- GitHub Actions workflow for automated Terraform deployment  
- Runs `terraform plan` and `terraform apply` on code changes  
- Safe deployment practices with plan review  

### Visual Documentation
- Screenshots showing each step of the workflow  
- GIFs demonstrate real-time progress for recruiters and hiring managers  

---

## 📋 Prerequisites

- AWS Account with GuardDuty permissions  
- Terraform installed locally  
- Git CLI for cloning the repository  
- AWS CLI configured with credentials (optional, for manual deployment)  

---

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/charles-bucher/cloudOps-guardDuty-automation.git
cd cloudOps-guardDuty-automation

# Initialize Terraform
terraform init

# Preview infrastructure
terraform plan

# Deploy GuardDuty
terraform apply
Type yes when prompted to confirm deployment.

⚠️ Always review the Terraform plan before applying in production accounts.

🎬 Visual Walkthrough
Step	Screenshot / GIF
1️⃣ GitHub Push	
2️⃣ Terraform Plan	
3️⃣ Terraform Plan Confirmation	
4️⃣ Terraform Apply	GIF showing Terraform apply in progress
5️⃣ GuardDuty Dashboard	GIF showing GuardDuty enabling in AWS Console

🗂 Repository Structure
bash
Copy code
cloudOps-guardDuty-automation/
├── .github/
│   └── workflows/
│       └── terraform-apply.yml   # GitHub Actions workflow
├── main.tf                      # Terraform main configuration
├── variables.tf                 # Terraform input variables
├── outputs.tf                   # Terraform outputs
├── README.md                    # This file
└── screenshots/
    └── GuardDuty/               # Screenshots & GIFs
🛠 What I Built (Technical Details)
Terraform Configuration

main.tf - AWS provider, GuardDuty detector, optional SNS/CloudWatch setup

variables.tf - Input variables for AWS region, GuardDuty config, notifications

outputs.tf - Outputs GuardDuty detector ID, findings URL, SNS topic ARN

CI/CD Pipeline

.github/workflows/terraform-apply.yml

Trigger: push to main branch

Steps: terraform fmt, terraform validate, terraform plan, optionally terraform apply

📊 What I Learned
Terraform state locking & remote state for team environments

IAM permissions troubleshooting

GitHub Actions secrets management for CI/CD

Version consistency across environments

🎯 Skills Demonstrated
Infrastructure-as-Code with Terraform

Security Automation & GuardDuty deployment

CI/CD Pipelines with GitHub Actions

AWS Security services (GuardDuty, CloudWatch Events, SNS)

Documentation with screenshots and GIFs

Error debugging: IAM, Terraform state, version conflicts

⚠️ Notes
Cost Awareness: GuardDuty analyzes CloudTrail events & VPC Flow Logs (~$5–10/month small accounts)

Security Best Practices: Never commit AWS credentials. Review Terraform plans. Use least-privilege IAM policies.

🤝 Contributing
Open issues or submit pull requests for:

Automation improvements

Additional monitoring integrations

Enhanced visual documentation

Bug fixes or optimizations

📄 License
MIT License – See LICENSE for details

📞 Contact
Email: charles.bucher.cloud@gmail.com

LinkedIn: Charles Bucher

GitHub: charles-bucher

🔍 Keywords for ATS / Recruiters
AWS, GuardDuty, Terraform, Infrastructure-as-Code, Security Automation, Threat Detection, CI/CD, GitHub Actions, CloudOps, Security Monitoring, Automated Deployment, DevSecOps

yaml



