# 🛡️ AWS GuardDuty Automation with Terraform

![License](https://img.shields.io/badge/license-MIT-blue)
![Terraform](https://img.shields.io/badge/Terraform-v1.0+-blue)
![AWS](https://img.shields.io/badge/AWS-GuardDuty-orange)
![CloudOps](https://img.shields.io/badge/CloudOps-Active-green)

Automated AWS security monitoring infrastructure deployed via Terraform. This project demonstrates enterprise-grade CloudOps practices by automating GuardDuty threat detection across AWS accounts with repeatable, version-controlled infrastructure.

---

## 📋 Table of Contents

- [What This Does](#what-this-does)
- [Why This Matters](#why-this-matters)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Quick Start](#-quick-start)
- [Architecture](#-architecture)
- [Visual Walkthrough](#-visual-walkthrough)
- [Project Structure](#-project-structure)
- [What I Learned](#-what-i-learned)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Connect With Me](#-connect-with-me)

---

## 🎯 What This Does

- Enables AWS GuardDuty automatically across accounts.
- Eliminates manual console setup.
- Deploys repeatable infrastructure using Terraform.
- Provides a portfolio-ready CloudOps/DevSecOps demonstration.

**Key Deliverables:**

- ✅ GuardDuty Enabled
- ✅ Infrastructure as Code (Terraform)
- ✅ Repeatable Deployments
- ✅ Security Baseline
- ✅ Portfolio-Ready

---

## 💡 Why This Matters

**Business Value:**

- Reduces security setup time from hours to minutes.
- Eliminates human error with IaC.
- Scales across multiple AWS accounts.
- Full audit trail via Git history.

**Technical Skills Demonstrated:**

- Terraform / IaC
- AWS GuardDuty, CloudWatch, IAM
- DevSecOps and CloudOps practices
- Git and version control
- Incident response automation

---

## 🛠️ Tech Stack

| Technology       | Purpose                  | Why It's Used                         |
|-----------------|--------------------------|--------------------------------------|
| Terraform        | Infrastructure as Code   | Standardized cloud automation        |
| AWS GuardDuty    | Threat Detection         | Monitors AWS accounts for threats    |
| AWS CloudWatch   | Logging & Monitoring     | Captures security findings           |
| GitHub Actions   | CI/CD Pipeline           | Automates deployments                |
| Git              | Version Control          | Tracks infrastructure changes        |

---

## 📦 Prerequisites

- AWS Account with admin access
- AWS CLI configured
- Terraform v1.0+
- Git installed
- IAM permissions for GuardDuty, CloudWatch, IAM role creation

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "guardduty:*",
        "iam:CreateServiceLinkedRole",
        "cloudwatch:*"
      ],
      "Resource": "*"
    }
  ]
}
🚀 Quick Start
Clone the repository:

bash
Copy code
git clone https://github.com/charles-bucher/cloudOps-guardDuty-automation.git
cd cloudOps-guardDuty-automation
Configure AWS credentials:

bash
Copy code
aws configure
# or export AWS_ACCESS_KEY_ID / AWS_SECRET_ACCESS_KEY
Initialize Terraform:

bash
Copy code
terraform init
Preview changes:

bash
Copy code
terraform plan
Deploy:

bash
Copy code
terraform apply
Verify GuardDuty:

bash
Copy code
aws guardduty list-detectors
Clean up (optional):

bash
Copy code
terraform destroy
🏗️ Architecture
markdown
Copy code
AWS Account
 ┌──────────────┐        ┌───────────────┐
 │ Terraform    │──────▶ │ AWS GuardDuty │
 │ Automation   │        │ Detector      │
 └──────────────┘        └───────┬───────┘
                                 │
                                 ▼
                           CloudWatch Logs
                           Security Events
Terraform manages the full infrastructure and deployment workflow.

🎬 Visual Walkthrough




🗂️ Project Structure
bash
Copy code
cloudOps-guardDuty-automation/
│
├── .github/workflows/       # GitHub Actions CI/CD
├── screenshots/             # Visual docs
├── main.tf                  # Core Terraform config
├── variables.tf             # Input variables
├── outputs.tf               # Output values
├── terraform.tfvars.example # Example variables
├── .gitignore
├── LICENSE
└── README.md
📚 What I Learned
Terraform state management and provider configuration

AWS IAM permissions and best practices

Infrastructure version control

Idempotent deployments

Security-first CloudOps principles

🔮 Future Enhancements
Short Term:

SNS Alerts for findings

Lambda incident response

Multi-region GuardDuty

Terraform modules

Long Term:

Export findings to S3

EventBridge integration

Terraform Cloud remote state

Cost optimization

CloudWatch/Grafana dashboards

🤝 Contributing
Fork repo

Create feature branch

Commit changes

Push branch

Open Pull Request

Areas for contribution: Terraform optimization, AWS security integrations, documentation, testing strategies.

📄 License
MIT License - see LICENSE file

📞 Connect With Me
GitHub: charles-bucher

LinkedIn: Charles Bucher

yaml
Copy code

