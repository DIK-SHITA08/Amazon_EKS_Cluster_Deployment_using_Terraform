# Terraform-Automated Amazon EKS Cluster

Production-ready EKS cluster deployment using Terraform. Fully automated — VPC, subnets, node groups, autoscaling, and IAM roles. Zero manual AWS console clicks.

## Architecture

[INSERT DIAGRAM HERE — use draw.io or Excalidraw]

## What Gets Provisioned
- Custom VPC with public/private subnets across 2 AZs
- EKS cluster with managed node groups
- Autoscaling configuration for worker nodes
- IAM roles and policies (least-privilege)
- Security groups and networking rules
- Outputs: cluster endpoint, kubeconfig, node group details

## Files
| File | Purpose |
|------|---------|
| `main.tf` | Provider configuration and backend |
| `vpc.tf` | VPC, subnets, route tables, NAT gateway |
| `eks-cluster.tf` | EKS cluster and node group definitions |
| `variables.tf` | Input variables (region, instance types, scaling) |
| `outputs.tf` | Cluster endpoint, security group IDs, etc. |
| `terraform.tf` | Terraform version and provider constraints |

## Usage
```bash
# Initialize Terraform
terraform init

# Preview changes
terraform plan

# Deploy
terraform apply

# Get kubeconfig
aws eks update-kubeconfig --name <cluster-name> --region <region>
```

## Security Considerations
- IAM roles follow least-privilege principle
- Worker nodes in private subnets
- Control plane logging enabled
- No hardcoded credentials — uses AWS provider chain

## Tech Stack
Terraform · AWS EKS · VPC · IAM · Auto Scaling

## Author
[Dikshita Deshmukh](https://www.linkedin.com/in/dikshita-deshmukh-7491941b8/) — DevOps Engineer
