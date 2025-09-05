# Terraform AWS VPC Project

This project provisions a **production-grade VPC** in AWS using Terraform.

## 📌 Features

- Creates a new **VPC**
- Configurable **Public and Private Subnets** across multiple AZs
- **Internet Gateway** for public subnets
- **NAT Gateway** for private subnets internet access
- **Route Tables** (public + private)
- Optional **Bastion Host** in public subnet

## 📂 Project Structure

```bash
terraform-vpc/
│── main.tf               
│── variables.tf          
│── terraform.tfvars     
│── outputs.tf            
│── provider.tf          
│
└── modules/
    └── vpc/
        ├── main.tf       
        ├── variables.tf  
        └── outputs.tf    
```

## 🚀 Usage

### 1️⃣ Initialize Terraform
```sh
terraform init
```

### 2️⃣ Validate Configuration
```sh
terraform validate
```

### 3️⃣ Plan Infrastructure
```sh
terraform plan -out tfplan
```

### 4️⃣ Apply Configuration
```sh
terraform apply tfplan
```

### 5️⃣ Destroy Resources (⚠️ Careful!)
```sh
terraform destroy
```

## 🛠️ Example `terraform.tfvars`
```hcl
aws_region          = "us-east-1"
vpc_cidr            = "10.0.0.0/16"
public_subnet_cidrs = ["10.0.1.0/24", "10.0.2.0/24"]
private_subnet_cidrs = ["10.0.11.0/24", "10.0.12.0/24"]
availability_zones  = ["us-east-1a", "us-east-1b"]
bastion_ami         = "ami-1234567890abcdef0"
instance_type       = "t2.micro"
```

## 📤 Outputs
- VPC ID
- Public Subnet IDs
- Private Subnet IDs
- Internet Gateway ID
- NAT Gateway ID
- Bastion Public IP

---

## 🐵 All In One VPC
- Direct usage of Modules from Terraform Registry make the code shorted and more readable. 


✅ This project is modular and reusable for any AWS environment.
