# AWS IAM + EC2 + S3 Access Control (Terraform)

## 🛡️ Overview

This project provisions an EC2 instance with restricted access to a private S3 bucket using IAM roles and Terraform.  
The goal: enforce least privilege by default and eliminate the need for hardcoded credentials in cloud workloads.

---

## 🚀 What It Demonstrates

- **IAM Role-to-Instance Binding** – Securely attach a scoped IAM role to an EC2 instance
- **Least Privilege Policy Design** – Define S3 access at the bucket + object level
- **Infrastructure-as-Code** – All resources managed via Terraform (modular, reproducible)
- **Credential Hygiene** – No hardcoded keys, no inline secrets

---

## 🧱 Tools & Services Used

- **AWS IAM** – Roles, policies, instance profiles
- **AWS EC2** – Ubuntu instance to test access controls
- **AWS S3** – Private bucket with restricted read access
- **Terraform** – Infrastructure provisioning
- **AWS CLI** – For manual access validation

---

## 🔍 Key Files

- `main.tf` – IAM role, policy, EC2 instance
- `s3.tf` – Bucket creation + policy block
- `outputs.tf` – Useful outputs (public IP, role name)
- `variables.tf` – Environment configuration

---

## 🧪 Test Cases

1. SSH into EC2 instance
2. Run `aws s3 ls s3://your-bucket-name`
3. Confirm access is allowed only from the EC2 instance with the attached IAM role
4. Attempt access from unauthenticated client (should fail)

---

## ✅ Why This Matters

Identity misconfiguration is the root cause of most cloud breaches.  
This project shows how to build IAM policies that:
- Minimize attack surface
- Bind access to workload identity (not users)
- Are reproducible and audit-friendly

---

## 📎 Bonus Ideas

- Extend to use **VPC endpoints** for private S3 access
- Add **CloudTrail logging** for audit visibility
- Wrap into a **Terraform module** for reuse across accounts

---

## 🔗 Live Project

[Back to my site → troyrcopeland.com](https://www.troyrcopeland.com)
