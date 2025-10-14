# lab-wk-7

## 1. Generate SSH Keys (ed25519)

The command below creates a new SSH key pair named **aws** using the ed25519. 

```bash
ssh-keygen -t ed25519 -f ~/.ssh/aws -C "acit4640_lab"
```

This will generate an ED25519 key pair and store it in

~/.ssh/aws (private key)

~/.ssh/aws.pub (public key)

## 2. Import SSH Key to AWS

Run the provided script to import the public key to AWS.

```
./import_lab_key ~/.ssh/aws.pub
```

This imports the public key into your AWS account allowing Terraform to associate it with EC2 instances.

## 3. Terraform Commands

```
cd terraform
```

```
terraform init
```

Initializes the Terraform working directory and downloads provider plugins.

```
terraform fmt
```

Formats Terraform configuration files for consistent style.

```
terraform validate
```


Validates the syntax and internal consistency of the configuration.

```
terraform plan
```
Creates the infrastructure.



Generates and displays an execution plan, showing what actions Terraform will take.

terraform apply
