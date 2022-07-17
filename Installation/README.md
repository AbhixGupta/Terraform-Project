# Terraform-Project

AWS Cloud based Terraform Project Repository.

For this project we will be using the l

### Installation of Terraform

To install the terraform go to this [TERRAFORM WEBSITE](https://www.terraform.io/downloads) and install the pakage according to your operating system.

#### Installation for Ubutu/Debian based Linux.

```bash
  wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
  echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
  sudo apt update && sudo apt install terraform
```

Now install the downloaded package.

```bash
  sudo apt-get update && sudo apt-get install -y gnupg software-properties-common curl
  curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
  sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
  sudo apt-get update && sudo apt-get install terraform
  terraform -help
  terraform -help plan
```

#### Installation for Amazon Linux

```bash
  sudo yum install -y yum-utils
  sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
  sudo yum -y install terraform
  terraform -help
  terraform -help plan
```

Next step is to download the [VS Code](https://code.visualstudio.com/download) and install the official HashiCrop Terraform VS code Plugin. After this install the latest version of [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) according to your operating system.

#### Configuration of AWS CLI

You have generate the Security Crendentials using AWS Management Console.
Go to Services -> IAM -> Users -> "Admin-User-Account" -> Security Credentials -> Now Create Access Key.

Open your respective operating system terminal and configure AWS credentials using SSH on your local desktop

```bash
  $ aws configure
  AWS Access Key ID [None]: AKIASUF7DEFKSIAWMZ7K
  AWS Secret Access Key [None]: WL9G9Tl8lGm7w9t7B3NEDny1+w3N/K5F3HWtdFH/
  Default region name [None]: us-east-1
  Default output format [None]: json

# Verify if we are able list S3 buckets
aws s3 ls
```

###

- init
- Validate
- Paln
- Apply
- Destroy
