# lab-wk-7

## 1. Generate SSH Keys (ed25519)

The command below creates a new SSH key pair named **aws** using the ed25519. 

```bash
ssh-keygen -t ed25519 -f ~/.ssh/aws -C "acit4640_lab"
```

This will generate an ED25519 key pair and store it in

~/.ssh/aws

~/.ssh/aws.pub 

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

Generates and displays an execution plan, showing what actions Terraform will take.

```
terraform apply
```
Creates the infrastructure.


## 4. Validate Ansible Configuration

Run syntax checks before applying the playbook.

```
cd ansible
ansible-playbook --syntax-check playbook.yml
```

What this command does is it verifies the playbook syntax is valid before execution.

## 5. Apply Ansible Playbook

Run the playbook to install and configure nginx on both instances.

```
ansible-playbook playbook.yml
```

This executes tasks defined in playbook.yml, including:

Installing nginx

Creating directory structure

Copying configuration files

Generating index.html from template

Reloading and enabling nginx service

## 6. Verify Deployment

Visit one of your server URLs in a web browser


```
http://<public_ip_or_dns>
```

## 7. Cleanup
 
This destroy all created resources and remove the imported AWS key.

```
cd terraform
terraform destroy
```
This will destroy the EC2 instances, VPC, and related infrastructure.

```
../delete_lab_key
```
The command above will delete our key pair
