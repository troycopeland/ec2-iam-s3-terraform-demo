# EC2 with IAM Role and S3 Access (Terraform)

This project uses Terraform to provision an AWS EC2 instance with an IAM role attached that allows **read-only access to S3**.

## 💡 Why This Project

This is a practical example of **infrastructure-as-code** and **least-privilege IAM design** — both are core cloud engineering skills.

- Provision AWS resources with Terraform
- Attach IAM roles to EC2 securely (no hardcoded credentials)
- Enforce scoped, read-only access to S3

## 🧰 What’s Included

- `aws_instance` for EC2 (Amazon Linux 2)
- `aws_iam_role` with assume-role trust policy
- `aws_iam_policy_attachment` for `AmazonS3ReadOnlyAccess`
- `aws_iam_instance_profile` to bind role to EC2
- `.gitignore` to exclude `.terraform/` and state files

## 📁 Folder Structure
.
├── main.tf               # Core Terraform configuration
├── .gitignore            # Excludes .terraform/ and tfstate

## ⚙️ How to Use

1. Clone this repo  
2. Set a valid AMI for your region in `main.tf`  
3. Make sure your AWS key pair is created and referenced  
4. Run:

   ```bash
   terraform init
   terraform apply