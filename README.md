# OCI Terraform VCN Setup

This repository provisions a basic Oracle Cloud Infrastructure (OCI) network using Terraform.

## 🔧 Components

The following infrastructure resources are created:

- **VCN** (`10.0.0.0/16`)
- **Public Subnet** (`10.0.1.0/24`)
- **Private Subnet** (`10.0.2.0/24`)
- **Internet Gateway**
- **NAT Gateway**
- **Route Tables** for public and private subnets
- **Security Lists** to allow SSH and HTTP traffic

## 📁 Files Overview

| File              | Description                                 |
|-------------------|---------------------------------------------|
| `vcn.tf`          | Creates the VCN, Internet Gateway, and Route Tables |
| `public_subnet.tf`| Provisions public subnet with IGW access    |
| `private_subnet.tf`| Provisions private subnet with NAT access  |
| `variables.tf`    | Input variables such as compartment OCID and AD |
| `.gitignore`      | Git ignore rules                            |

## 🚀 Usage

### 1. Clone the repository

```bash
git clone https://github.com/vigneshkattamudi/oci-terraform-vcn.git
cd oci-terraform-vcn
````

### 2. Configure your variables

Create a `terraform.tfvars` file with:

```hcl
compartment_ocid    = "ocid1.compartment.oc1..xxxx"
availability_domain = "ocid1.availabilitydomain.oc1..xxxx"
ssh_public_key      = "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQ..."
```

### 3. Deploy infrastructure

```bash
terraform init
terraform apply
```

## 🧹 Cleanup

To destroy the infrastructure:

```bash
terraform destroy
```

## 🧑 Author

[Vignesh Kattamudi](https://github.com/vigneshkattamudi)
