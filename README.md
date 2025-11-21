# 🛡️ AWS GuardDuty Automation with Terraform

[![Terraform](https://img.shields.io/badge/Terraform-1.0+-623CE4?style=for-the-badge&logo=terraform&logoColor=white)](https://www.terraform.io/)
[![AWS](https://img.shields.io/badge/AWS-GuardDuty-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/guardduty/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![Maintained](https://img.shields.io/badge/Maintained-Yes-brightgreen.svg?style=for-the-badge)](https://github.com/charles-bucher/cloudOps-guardDuty-automation)

> **Automated AWS security monitoring infrastructure deployed via Terraform. This project demonstrates enterprise-grade CloudOps practices by automating GuardDuty threat detection across AWS accounts with repeatable, version-controlled infrastructure.**

---

## 📋 Table of Contents

- [What This Does](#-what-this-does)
- [Why This Matters](#-why-this-matters)
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

---

## 🎯 What This Does

This project automates the deployment of AWS GuardDuty using Terraform, eliminating manual console clicking and creating a reproducible security monitoring foundation. 

**In plain English:** Instead of logging into AWS and manually enabling GuardDuty through multiple screens, this code does it automatically and consistently across any AWS account.

### Key Deliverables

✅ **GuardDuty Enabled** - Automatic threat detection across your AWS environment  
✅ **Infrastructure as Code** - Entire setup defined in version-controlled Terraform  
✅ **Repeatable Deployments** - Deploy to dev, staging, and production identically  
✅ **Security Baseline** - Foundation for automated incident response  
✅ **Portfolio-Ready** - Real-world CloudOps/DevSecOps demonstration

---

## 💡 Why This Matters

### Business Value
- **Reduces Security Setup Time:** From hours of manual work to minutes of automated deployment
- **Eliminates Human Error:** Infrastructure as Code ensures consistent, correct configuration every time
- **Scales Across Accounts:** Deploy identical security posture to multiple AWS accounts with one command
- **Audit Trail Built-In:** Git history provides complete deployment documentation for compliance

### Technical Skills Demonstrated
- **Infrastructure as Code (IaC)** - Terraform for cloud automation
- **AWS Security Services** - GuardDuty configuration and management
- **DevSecOps Practices** - Integrating security into deployment pipelines
- **Version Control** - Git-based infrastructure management
- **Cloud Operations** - Real-world AWS resource provisioning

---

## 🛠️ Tech Stack

| Technology | Purpose | Why It's Used |
|------------|---------|---------------|
| **Terraform** | Infrastructure as Code | Industry-standard tool for cloud automation |
| **AWS GuardDuty** | Threat Detection | Monitors AWS accounts for malicious activity |
| **AWS CloudWatch** | Logging & Monitoring | Captures security findings and events |
| **GitHub Actions** | CI/CD Pipeline | Automates deployment workflow |
| **Git** | Version Control | Tracks infrastructure changes over time |

---

## 📦 Prerequisites

Before you begin, ensure you have:

- **AWS Account** with administrative access
- **AWS CLI** configured with credentials ([Installation Guide](https://aws.amazon.com/cli/))
- **Terraform** v1.0+ installed ([Download](https://www.terraform.io/downloads))
- **Git** for cloning the repository
- **IAM Permissions** for GuardDuty, CloudWatch, and IAM role creation

### AWS Permissions Required
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
```

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/charles-bucher/cloudOps-guardDuty-automation.git
cd cloudOps-guardDuty-automation
```

### 2. Configure AWS Credentials
```bash
# Option 1: Using AWS CLI
aws configure

# Option 2: Export environment variables
export AWS_ACCESS_KEY_ID="your-access-key"
export AWS_SECRET_ACCESS_KEY="your-secret-key"
export AWS_DEFAULT_REGION="us-east-1"
```

### 3. Initialize Terraform
```bash
terraform init
```
This downloads the AWS provider and prepares your workspace.

### 4. Preview the Changes
```bash
terraform plan
```
Review what resources will be created before applying.

### 5. Deploy the Infrastructure
```bash
terraform apply
```
Type `yes` when prompted to confirm deployment.

### 6. Verify GuardDuty is Enabled
```bash
# Check via AWS CLI
aws guardduty list-detectors

# Or visit the AWS Console
# Navigate to: GuardDuty → Summary
```

### 7. Clean Up (Optional)
```bash
terraform destroy
```
Removes all created resources to avoid charges.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    AWS Account                          │
│                                                         │
│  ┌──────────────┐         ┌─────────────────┐         │
│  │   Terraform  │────────▶│  AWS GuardDuty  │         │
│  │   Automation │         │    Detector     │         │
│  └──────────────┘         └────────┬────────┘         │
│                                    │                    │
│                                    ▼                    │
│                          ┌──────────────────┐          │
│                          │  CloudWatch Logs │          │
│                          │  Security Events │          │
│                          └──────────────────┘          │
│                                                         │
└─────────────────────────────────────────────────────────┘

                            ▲
                            │
                     Terraform manages
                  entire infrastructure
```

### How It Works

1. **Terraform Reads Configuration** - Parses `.tf` files to understand desired state
2. **AWS API Calls** - Terraform communicates with AWS to create resources
3. **GuardDuty Activation** - Detector is enabled and begins monitoring
4. **Continuous Monitoring** - GuardDuty analyzes VPC Flow Logs, DNS logs, and CloudTrail events
5. **Finding Generation** - Security threats trigger findings in GuardDuty dashboard

---

## 🎬 Visual Walkthrough

### Step 1: GitHub Push
![GitHub Push](screenshots/01-github-push.png)
*Code pushed to GitHub repository triggering version control*

### Step 2: Terraform Plan
![Terraform Plan](screenshots/02-terraform-plan.png)
*Preview of infrastructure changes before deployment*

### Step 3: Terraform Apply
![Terraform Apply](screenshots/03-terraform-apply.gif)
*Real-time deployment showing resource creation*

### Step 4: GuardDuty Enabled
![GuardDuty Dashboard](screenshots/04-guardduty-enabled.gif)
*GuardDuty active and monitoring for security threats*

---

## 🗂️ Project Structure

```
cloudOps-guardDuty-automation/
│
├── .github/
│   └── workflows/
│       └── terraform-apply.yml      # GitHub Actions CI/CD pipeline
│
├── screenshots/                     # Visual documentation
│   ├── 01-github-push.png
│   ├── 02-terraform-plan.png
│   ├── 03-terraform-apply.gif
│   └── 04-guardduty-enabled.gif
│
├── main.tf                          # Core Terraform configuration
├── variables.tf                     # Input variables for customization
├── outputs.tf                       # Output values after deployment
├── terraform.tfvars.example         # Example variable values
├── .gitignore                       # Files excluded from version control
├── LICENSE                          # MIT License
└── README.md                        # This file
```

### Key Files Explained

- **`main.tf`** - Defines AWS GuardDuty detector and related resources
- **`variables.tf`** - Parameterizes the deployment (region, naming, etc.)
- **`outputs.tf`** - Displays important info after deployment (detector ID, etc.)
- **`.github/workflows/`** - Automates Terraform deployment via GitHub Actions

---

## 📚 What I Learned

Building this project taught me real-world CloudOps skills that companies actively look for:

### Technical Skills
- **Terraform State Management** - How to handle infrastructure state files safely
- **AWS IAM Permissions** - Configuring least-privilege access for GuardDuty
- **Provider Configuration** - Managing AWS provider versions and authentication
- **Resource Dependencies** - Ensuring resources are created in the correct order

### Best Practices
- **Version Control for Infrastructure** - Treating infrastructure like application code
- **Documentation** - Creating clear READMEs that help others (and future me) understand the project
- **Idempotency** - Writing code that can be run multiple times with the same result
- **Security First** - Never hardcoding credentials, using environment variables instead

### Challenges Overcome
1. **AWS Permissions Issues** - Learned to debug IAM policy errors by reading CloudTrail logs
2. **Terraform State Conflicts** - Understood backend configuration for team collaboration
3. **Provider Version Compatibility** - Pinned Terraform provider versions for stability

---

## 🔮 Future Enhancements

This is a living project. Here's what I'm planning to add:

### Short Term
- [ ] **SNS Notifications** - Email/SMS alerts when GuardDuty finds threats
- [ ] **Lambda Integration** - Automated incident response to high-severity findings
- [ ] **Multi-Region Support** - Deploy GuardDuty across all AWS regions simultaneously
- [ ] **Terraform Modules** - Refactor into reusable modules for larger organizations

### Long Term
- [ ] **S3 Finding Export** - Archive GuardDuty findings to S3 for compliance
- [ ] **EventBridge Integration** - Route findings to security orchestration tools
- [ ] **Terraform Cloud** - Remote state management and team collaboration
- [ ] **Cost Optimization** - Implement GuardDuty intelligent threat detection to reduce costs

### Portfolio Expansion
- [ ] Add Terraform testing with `terraform test`
- [ ] Integrate with Security Hub for centralized finding management
- [ ] Create Ansible playbooks for post-deployment configuration
- [ ] Build dashboards with CloudWatch or Grafana for visualization

---

## 🤝 Contributing

I'm actively learning and improving this project. Contributions, suggestions, and feedback are welcome!

### How to Contribute
1. Fork this repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit with clear messages (`git commit -m "Add SNS notification support"`)
5. Push to your fork (`git push origin feature/improvement`)
6. Open a Pull Request

### Areas Where I'd Love Help
- Terraform best practices and optimization
- Additional AWS security service integrations
- Documentation improvements
- Testing strategies for infrastructure code

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**TL;DR:** You can use, modify, and distribute this code freely. Just include the original license.

---

## 🙏 Acknowledgments

- **AWS Documentation** - For comprehensive GuardDuty guides
- **Terraform Registry** - For AWS provider examples and modules
- **CloudOps Community** - For sharing best practices and troubleshooting tips

---

## 📞 Connect With Me

I'm actively seeking remote opportunities in CloudOps, DevOps, and Security Automation.

[![GitHub](https://img.shields.io/badge/GitHub-charles--bucher-181717?style=for-the-badge&logo=github)](https://github.com/charles-bucher)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/charles-bucher)

---

## ⚡ Quick Reference

### Useful Commands
```bash
# Initialize Terraform
terraform init

# Format Terraform files
terraform fmt

# Validate configuration
terraform validate

# Preview changes
terraform plan

# Apply changes
terraform apply

# Destroy infrastructure
terraform destroy

# Show current state
terraform show

# List all resources
terraform state list
```

### Troubleshooting

**Issue:** `Error: error enabling GuardDuty detector`  
**Solution:** Check IAM permissions and ensure GuardDuty isn't already enabled

**Issue:** `Error: error configuring Terraform AWS Provider`  
**Solution:** Verify AWS credentials with `aws sts get-caller-identity`

**Issue:** Terraform state lock errors  
**Solution:** Ensure no other Terraform process is running, or use `terraform force-unlock`

---

<div align="center">

**⭐ If this project helped you, please consider giving it a star!**

*Built with ☕ and determination by Charles Bucher*

</div>