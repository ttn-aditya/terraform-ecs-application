# terraform-ecs-application
A complete application set which applies IAM , created VPC and then launches ECS cluster for a live and running application

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| ecs-cluster-name | The name for the cluster. | `string` | `"Cactus-ecs-cluster"` | no |
| ecs-key-pair-name | The name for the cluster. | `string` | `"Cactus"` | no |

# EC2

## Providers

| Name | Version |
|------|---------|
| aws | n/a |
| template | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| autoscaling-group-name | The name for the autoscaling group for the cluster. | `string` | `"Cactus-ecs-asg"` | no |
| desired-capacity | The name for the autoscaling group for the cluster. | `number` | `3` | no |
| ecs-cluster-name | n/a | `any` | n/a | yes |
| ecs-instance-profile-name | n/a | `any` | n/a | yes |
| ecs-instance-role-name | n/a | `any` | n/a | yes |
| ecs-key-pair-name | n/a | `any` | n/a | yes |
| health-check-grace-period | The name for the autoscaling group for the cluster. | `number` | `300` | no |
| image-id | The name for the autoscaling group for the cluster. | `string` | `"ami-d61027ad"` | no |
| instance-type | The name for the autoscaling group for the cluster. | `string` | `"t2.medium"` | no |
| launch-configuration-name | The name for the autoscaling group for the cluster. | `string` | `"Cactus-ecs-launch-configuration"` | no |
| load-balancer-name | The name for the autoscaling group for the cluster. | `string` | `"Cactus-ecs-load-balancer"` | no |
| max-instance-size | The name for the autoscaling group for the cluster. | `number` | `5` | no |
| min-instance-size | The name for the autoscaling group for the cluster. | `number` | `2` | no |
| security-group-id | n/a | `any` | n/a | yes |
| subnet-id-1 | n/a | `any` | n/a | yes |
| subnet-id-2 | n/a | `any` | n/a | yes |
| target-group-name | The name for the autoscaling group for the cluster. | `string` | `"Cactus-ecs-target-group"` | no |
| vpc-id | n/a | `any` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| ecs-load-balancer-name | n/a |
| ecs-target-group-arn | n/a |

# ECS

## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| ecs-cluster-name | n/a | `string` | `"Cactus-ecs-cluster"` | no |
| ecs-load-balancer-name | n/a | `string` | `"Cactus-ecs-load-balancer"` | no |
| ecs-service-name | n/a | `string` | `"Cactus-ecs-service"` | no |
| ecs-service-role-arn | n/a | `string` | `"Cactus-ecs-cluster"` | no |
| ecs-target-group-arn | n/a | `any` | n/a | yes |

# iam

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

No input.

## Outputs

| Name | Description |
|------|-------------|
| ecs-instance-profile-name | n/a |
| ecs-instance-role-name | n/a |
| ecs-service-role-arn | n/a |

# VPC

## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

No input.

## Outputs

| Name | Description |
|------|-------------|
| id | n/a |
| security-group-id | n/a |
| subnet1-id | n/a |
| subnet2-id | n/a |


## Directory structure

[34;42m.[00m
├── [01;32mREADME.md[00m
├── [34;42mec2[00m
│   ├── [01;32mautoscaling-group.tf[00m
│   ├── [01;32melastic-load-balancer.tf[00m
│   ├── [01;32mlaunch-configuration.tf[00m
│   ├── [01;32muser-data.tpl[00m
│   └── [01;32mvariable.tf[00m
├── [34;42mecs[00m
│   ├── [01;32mcluster.tf[00m
│   ├── [01;32mservice.tf[00m
│   ├── [01;32mtask-definition.json[00m
│   ├── [01;32mtask-definition.tf[00m
│   └── [01;32mvariables.tf[00m
├── [01;32mgraph.svg[00m
├── [34;42miam[00m
│   ├── [01;32mecs-instance-profile.tf[00m
│   ├── [01;32mecs-instance-role.tf[00m
│   └── [01;32mecs-service-role.tf[00m
├── [01;32mmain.tf[00m
├── [01;32mmy.md[00m
├── [01;32mvariable.tf[00m
└── [34;42mvpc[00m
    ├── [01;32minternet-gateway.tf[00m
    ├── [01;32mnetwork-acl.tf[00m
    ├── [01;32mroute-table.tf[00m
    ├── [01;32msecurity-group.tf[00m
    ├── [01;32msubnet.tf[00m
    └── [01;32mvpc.tf[00m

4 directories, 24 files
