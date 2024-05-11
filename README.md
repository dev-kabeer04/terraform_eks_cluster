Terraform EKS Cluster Setup

This Terraform project automates the provisioning of an Amazon EKS (Elastic Kubernetes Service) cluster on AWS along with associated networking and IAM resources.

Prerequisites
Before you begin, ensure you have the following installed:

Terraform (version X.X.X)

AWS CLI
kubectl
Additionally, make sure you have configured AWS CLI with the necessary access credentials.

Usage
Clone this repository:

bash
Copy code
git clone <repository-url>
Navigate to the project directory:

bash
Copy code
cd terraform-eks-cluster
Initialize Terraform:

bash
Copy code
terraform init
Review and customize the terraform.tfvars file according to your requirements.

Plan the infrastructure changes:

bash
Copy code
terraform plan
Apply the Terraform configuration to create the EKS cluster and associated resources:

bash
Copy code
terraform apply
Once the cluster is created, configure kubectl to connect to the cluster:

bash
Copy code
aws eks --region ap-south-1 update-kubeconfig --name eks-cluster
Verify that kubectl is configured correctly:

bash
Copy code
kubectl get svc
Clean up (optional):

bash
Copy code
terraform destroy

Directory Structure

main.tf: Contains the main Terraform configuration for provisioning resources.
variables.tf: Defines input variables used in the Terraform configuration.
terraform.tfvars: Specifies values for the input variables.
outputs.tf: Defines outputs for the Terraform resources.
.gitignore: Specifies files and directories to be ignored by Git.
Resources Created
Amazon EKS cluster
Worker nodes (managed node group)
Virtual Private Cloud (VPC)
Internet Gateway (IGW)
Subnets
NAT Gateways
Routes
IAM OIDC Provider
EKS Add-ons (e.g., Kubernetes Dashboard, CoreDNS)
IAM Roles and Policies

Contributing

Contributions are welcome! If you find any issues or want to enhance the project, feel free to open a pull request.


Feel free to further customize this README template to include any additional details or instructions specific to your project.