## AWS 

- **Whats is AWS**  
  AWS (Amazon Web Services) is a cloud computing platform provided by Amazon.
It allows individuals and businesses to rent computing resources like servers, storage, and databases over the internet, instead of buying and maintaining physical hardware.

- **AWS Region**  
  A geographical location where AWS has data centers.  
  Example: us-east-1, ap-south-1.

- **Availability Zone (AZ)**  
  An isolated data center within a region.  
  Multiple AZs help achieve high availability.

- **EC2 (Elastic Compute Cloud)**  
  A service that provides scalable virtual servers in the cloud.  
  Used to host applications and services.

- **AMI (Amazon Machine Image)**  
  A template containing the operating system and configuration.  
  Used to launch EC2 instances.

- **Instance Type**  
  Determines CPU, memory, and network capacity of an EC2 instance.  
  Example: t2.micro (free-tier eligible).

- **Key Pair**  
  Used to securely connect to EC2 instances via SSH.  
  The private key is stored by the user.

- **Security Group**  
  Acts as a virtual firewall controlling inbound and outbound traffic.  
  Rules allow specific ports and IP ranges.

- **VPC (Virtual Private Cloud)**  
  A logically isolated virtual network in AWS.  
  EC2 instances run inside a VPC.

- **IAM (Identity and Access Management)**  
  Controls access to AWS services and resources.  
  Permissions are defined using policies.

---

## Manual EC2 Instance Setup (AWS Console)

### Steps Followed:
1. Logged into AWS Management Console.
2. Navigated to EC2.
3. Launch Instance.
4. Selected Amazon Linux 2 AMI.
5. Need to Chose instance type eg: t2.micro.
6. Created a key pair for SSH access.
7. Configured a security group allowing SSH (port 22).
8. Launched the EC2 instance.
9. Verified instance status as running.

---

## Terraform

- **Whats is Terraform**  

Terraform is an Infrastructure as Code (IaC) tool used to provision and manage cloud resources using declarative configuration files.

### Key Components:
- **Provider**: Plugin to interact with AWS.
- **Resource**: Defines AWS resources such as EC2.
- **State**: Tracks the current infrastructure.
- **Plan**: Shows changes before applying.
- **Apply**: Creates or updates infrastructure.

---

## EC2 Provisioning Using Terraform

### Terraform Files:
- `main.tf` – Defines provider and EC2 resource
- `variables.tf` – Input variables(optional)

### resource "aws_instance" "example" { ... }
- resource → Tells Terraform you want to create/manage a resource.
- "aws_instance" → The type of resource. Here, it’s an EC2 instance in AWS.
- "example" → The name of this resource in Terraform.

### Commands Used:
```bash
terraform init (Initializes a Terraform working directory.)
terraform plan (Shows a preview of changes Terraform will make to your infrastructure.)
terraform apply (Creates or updates EC2, S3, or other resources)

### Task completed:

Learn core AWS EC2 concepts
Launch EC2 instance manually via AWS Console
Provision EC2 instance using Terraform
Document the process