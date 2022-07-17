# Basic Commands

Before moving furthur make sure to have these conditions fulfilled:

- Ensure you have default-vpc in that respective region
- Ensure AMI you are provisioning exists in that region if not update AMI ID
- Verify your AWS Credentials in $HOME/.aws/credentials

```bash
  # Terraform Settings Block
  terraform {
    required_providers {
      aws = {
        source  = "hashicorp/aws"
        #version = "~> 3.21" # Optional but recommended in production
      }
    }
  }

  # Provider Block
    provider "aws" {
    profile = "default" # AWS Credentials Profile configured on your local desktop terminal  $HOME/.aws/credentials
    region  = "us-east-1"
  }

  # Resource Block
  resource "aws_instance" "ec2demo" {
    ami           = "ami-04d29b6f966df1537" # Amazon Linux in us-east-1, update as per your region
    instance_type = "t2.micro"
  }
```

Now you have to series of commad to launch the terraform configuratino.

```bash
  # Initialize Terraform
  terraform init

  # Terraform Validate
  terraform validate

  # Terraform Plan to Verify what it is going to create / update / destroy
  terraform plan

  # Terraform Apply to Create EC2 Instance
  terraform apply
```

Goto your EC2 instance and check the launched VM.

#### Destroy the Instance

```bash
  # TO destroy EC2 Instance
  terraform destroy

  # To delete Terraform files
  rm -rf .terraform*
  rm -rf terraform.tfstate*
```
