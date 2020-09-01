# terraform-terraform-template
Template repository for terraform modules. Good for any cloud and any provider.

[![tflint](https://github.com/rhythmictech/terraform-terraform-template/workflows/tflint/badge.svg?branch=master&event=push)](https://github.com/rhythmictech/terraform-terraform-template/actions?query=workflow%3Atflint+event%3Apush+branch%3Amaster)
[![tfsec](https://github.com/rhythmictech/terraform-terraform-template/workflows/tfsec/badge.svg?branch=master&event=push)](https://github.com/rhythmictech/terraform-terraform-template/actions?query=workflow%3Atfsec+event%3Apush+branch%3Amaster)
[![yamllint](https://github.com/rhythmictech/terraform-terraform-template/workflows/yamllint/badge.svg?branch=master&event=push)](https://github.com/rhythmictech/terraform-terraform-template/actions?query=workflow%3Ayamllint+event%3Apush+branch%3Amaster)
[![misspell](https://github.com/rhythmictech/terraform-terraform-template/workflows/misspell/badge.svg?branch=master&event=push)](https://github.com/rhythmictech/terraform-terraform-template/actions?query=workflow%3Amisspell+event%3Apush+branch%3Amaster)
[![pre-commit-check](https://github.com/rhythmictech/terraform-terraform-template/workflows/pre-commit-check/badge.svg?branch=master&event=push)](https://github.com/rhythmictech/terraform-terraform-template/actions?query=workflow%3Apre-commit-check+event%3Apush+branch%3Amaster)

## Example
Here's what using the module will look like
```hcl
module "example" {
  source = "rhythmictech/terraform-mycloud-mymodule
}
```

## About
A bit about this module

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | == 0.13.1 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |
| spotinst | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| cluster\_name | Cluster name | `string` | n/a | yes |
| max\_size | The upper limit of worker nodes the Ocean cluster can scale up to | `number` | n/a | yes |
| min\_size | The lower limit of worker nodes the Ocean cluster can scale down to | `number` | n/a | yes |
| region | The region the EKS cluster will be located | `string` | n/a | yes |
| spotinst\_account | Spotinst account ID | `string` | n/a | yes |
| spotinst\_token | Spotinst Personal Access token | `string` | n/a | yes |
| ami\_id | The image ID for the EKS worker nodes. If none is provided, Terraform will search for the latest version of their EKS optimized worker AMI based on platform | `string` | `null` | no |
| associate\_public\_ip\_address | Associate a public IP address to worker nodes | `bool` | `false` | no |
| cidr | The CIDR block for the VPC. Default value is a valid CIDR, but not acceptable by AWS and should be overridden (only needed if new vpc is created) | `string` | `"0.0.0.0/0"` | no |
| cluster\_identifier | Cluster identifier | `string` | `null` | no |
| cluster\_version | Kubernetes supported version | `string` | `"1.17"` | no |
| create\_vpc | Controls if VPC should be created (it affects almost all resources) | `bool` | `true` | no |
| key\_name | The key pair to attach to the worker nodes launched by Ocean | `string` | `null` | no |
| private\_subnet\_ids | A ID's of private subnets inside the VPC (only needed if no vpc is created) | `list(string)` | `[]` | no |
| private\_subnets | A list of private subnets inside the VPC (only needed if new vpc is created) | `list(string)` | `[]` | no |
| public\_subnets | A list of public subnets inside the VPC (only needed if new vpc is created) | `list(string)` | `[]` | no |
| vpc\_id | The ID of the VPC (only needed if no vpc is created) | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| cluster\_endpoint | The endpoint for your EKS Kubernetes API |
| cluster\_id | The name/id of the EKS cluster |
| cluster\_security\_group\_id | Security group ID attached to the EKS cluster |
| config\_map\_aws\_auth | A Kubernetes configuration to authenticate to this EKS cluster |
| kubeconfig | kubectl config file contents for this EKS cluster |
| kubeconfig\_filename | The filename of the generated kubectl config |
| worker\_iam\_role\_arn | Default IAM role ARN for EKS worker groups |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## The Giants Underneath this Module
- [pre-commit.com](pre-commit.com)
- [terraform.io](terraform.io)
- [github.com/tfutils/tfenv](github.com/tfutils/tfenv)
- [github.com/segmentio/terraform-docs](github.com/segmentio/terraform-docs)
