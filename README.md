# DPS-INFRA

## Overview
* This repository contains Terraform configurations and resources to create an Amazon EKS cluster with a node group on AWS. Amazon EKS is a managed Kubernetes service that simplifies the deployment, management, and scaling of containerized applications using Kubernetes.
* Also contains Yaml Files that deploys actual services, deployments, to EKS cluster.

## Resources used to create cluster
All these resources are created through Terraform Scripts
* VPC
  * Private Subnets
  * Public Subnets 
  * Internet Gateway
  * NAT Gateway
  * Security Groups
* EKS
  * EKS cluster
    * Node Group
      * Contains Two Nodes, These Nodes are part of Auto Scaling Group, they scale as per the workload traffic.
* ELB(Elastic Load Balacer)
  * We are installing AWS load balancer controller in the cluster
  * This Controller creates external/internal load balancer in AWS as per the configuration, and takes the incoming public traffic

**To achieve this we need to run these below commands:**
  * Be in the folder that has terraform scripts `.tf` files.

```
`terraform init`
``` 
```
`terraform validate`
```
```
`terraform fmt`
```
```
`terraform plan`
```
```
`terraform apply`
```

## Applying YAML Files
* These Yaml files creates services like 
  * ClusterIP (It provides Internal communications between pods only inside the cluster)
  * LoadBlancer (This service expose api service to public traffic) 
  * Deployment (It deploys ECR images as pods with high availability)

**To achieve this we need to run these below command:**
  * Be in the folder that has YAML scripts.

```
`kubectl apply -f .`
``` 










