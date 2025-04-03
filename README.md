## Terraform with aws provider

## Terraform with AWS

### Overview
This repository contains Terraform configurations to set up and manage AWS infrastructure. It includes scripts for managing resources like EC2 instances, S3 buckets, IAM roles, and more using Infrastructure as Code (IaC).

## Prerequisites
Ensure you have the following installed before using the Terraform scripts:

- [Terraform](https://developer.hashicorp.com/terraform/downloads)
- [AWS CLI](https://aws.amazon.com/cli/)
- AWS IAM user with necessary permissions

## Project Structure
```
Terraform_with_aws/
│── AWS/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│── local_state/
│── remote_state/
│── README.md
```

## Getting Started
### 1. Configure AWS CLI
```sh
aws configure
```
Provide your AWS **Access Key**, **Secret Key**, **Region**, and **Output Format** when prompted.

### 2. Initialize Terraform
```sh
terraform init
```
This initializes the Terraform working directory and downloads the necessary provider plugins.

### 3. Plan Infrastructure Changes
```sh
terraform plan
```
This command previews the changes Terraform will make to your AWS infrastructure.

### 4. Apply the Configuration
```sh
terraform apply -auto-approve
```
This will create the resources defined in `main.tf`.

### 5. Verify Resources
Once the deployment is complete, you can verify the resources using AWS CLI:
```sh
aws ec2 describe-instances
```

### 6. Destroy Resources (If Needed)
To remove all infrastructure managed by Terraform:
```sh
terraform destroy -auto-approve
```

## Using Remote State
To store Terraform state remotely (e.g., in an S3 bucket), update `backend` configuration in `remote_state/main.tf` and run:
```sh
terraform init -reconfigure
```

## Best Practices
- Use remote backend for state management.
- Store sensitive data securely using AWS Secrets Manager or SSM.
- Implement Terraform modules for reusable infrastructure components.

## Contributing
Feel free to fork this repo and submit pull requests for improvements.

## License
This project is licensed under the MIT License.

---
🚀 **Happy Terraforming!**

