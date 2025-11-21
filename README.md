# AWS GuardDuty Automation with Terraform

[![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white)](https://www.terraform.io/)
[![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github&logoColor=white)](https://github.com/features/actions)
[![CloudOps](https://img.shields.io/badge/CloudOps-00ff94?style=for-the-badge)](https://github.com/charles-bucher)

Automated AWS GuardDuty deployment using **Terraform** for security threat detection and CloudOps automation. Fully CI/CD-enabled with GitHub Actions and portfolio-ready visual documentation.

---

## 🎯 What This Project Does
- Automates GuardDuty deployment across AWS accounts.
- Provides real-time security findings notifications.
- Implements repeatable, auditable Infrastructure-as-Code.
- Includes GitHub Actions CI/CD pipeline for automation.
- Portfolio-ready visual walkthroughs with screenshots and GIFs.

---

## 🔑 Key Features

**Infrastructure as Code**
- Terraform automates entire GuardDuty setup.
- Version-controlled config files: `main.tf`, `variables.tf`, `outputs.tf`.
- Repeatable, auditable deployments across multiple AWS accounts.

**Security Monitoring**
- Detects compromised credentials, crypto-mining, unauthorized access.
- Real-time alerts via CloudWatch/SNS.
- Extensible for Lambda or custom monitoring rules.

**CI/CD Pipeline**
- GitHub Actions workflow automates Terraform deployment.
- Runs `terraform plan` and `terraform apply` on code changes.
- Safe deployment with plan review.

**Visual Documentation**
- Screenshots and GIFs of deployment workflow for portfolio impact.

---

## 📋 Prerequisites
- AWS Account with GuardDuty permissions
- Terraform installed locally
- Git CLI for cloning
- AWS CLI configured (optional, for manual deployment)

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
# Type "yes" to confirm
⚠️ Always review the Terraform plan before deploying in production accounts.

🎬 Visual Walkthrough
Step	Screenshot / GIF
1️⃣ GitHub Push	
2️⃣ Terraform Plan	
3️⃣ Terraform Apply	
4️⃣ GuardDuty Dashboard	GIF showing GuardDuty enabling in AWS Console

GIFs demonstrate real-time progress for recruiters.

🗂 Repository Structure
bash
Copy code
cloudOps-guardDuty-automation/
├── .github/
│   └── workflows/terraform-apply.yml
├── main.tf
├── variables.tf
├── outputs.tf
├── README.md
└── screenshots/
    └── GuardDuty/  # Screenshots & GIFs
🛠 Technical Details
main.tf: AWS provider, GuardDuty detector, optional SNS/CloudWatch.

variables.tf: AWS region, GuardDuty config, notifications.

outputs.tf: Detector ID, findings URL, SNS ARN.

CI/CD: .github/workflows/terraform-apply.yml triggers on push, runs format, validate, plan, and apply.

📊 Lessons Learned
Terraform state management and remote state configuration.

IAM permission troubleshooting.

GitHub Actions secrets for CI/CD.

Version consistency across environments.

🎯 Skills Demonstrated
Infrastructure-as-Code (Terraform)

Security Automation & GuardDuty deployment

CI/CD Pipelines (GitHub Actions)

AWS Security Services (GuardDuty, CloudWatch, SNS)

Documentation with screenshots/GIFs

Debugging IAM, Terraform state, and version conflicts

⚠️ Notes
Cost Awareness: GuardDuty analyzes CloudTrail & VPC Flow Logs (~$5–10/month for small accounts)

Security Best Practices: Do not commit AWS credentials, review Terraform plans, least-privilege IAM policies

🤝 Contributing
Open issues or submit PRs for:

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

🔍 Keywords
AWS, GuardDuty, Terraform, Infrastructure-as-Code, Security Automation, CI/CD, GitHub Actions, CloudOps, Security Monitoring, DevSecOps, Cloud Security, Automated Deployment

yaml
Copy code
