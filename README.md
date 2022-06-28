# What The Hack: Infrastructure As Code with Bicep

## Introduction

DevOps is a journey not a destination. Implementing Infrastructure-as-Code is one of the first steps you will need to take!

When implementing an application environment in the cloud, it is important to have a repeatable way to deploy the underlying infrastructure components as well as your software into the target environment.  This includes resources such as:
- Virtual Networks, Network Security Groups (Firewalls), Public IPs, Virtual Machines, Storage (Disks)
- PaaS Services (Azure SQL, App Service, etc)
- Configuration Management (installing & configuring software on VMs)

The best way to make deployments repeatable is to define them with code, hence the term "Infrastructure as Code" (aka IAC).  There are multiple technologies that enable you to achieve this. Some of these include:
- ARM Templates with JSON
- Azure Bicep
- PowerShell Desired State Configuration (DSC)
- HashiCorp's Terraform & Packer
- Ansible, Chef, Puppet, Salt Stack, and others

This hack is focused on using Bicep to implement your IaC. It does not mean this is the only way to implement IaC, it's just one of many ways.

## Learning Objectives

This hack will help you learn:
- How Bicep can be used to deploy Azure infrastructure

The challenges build upon each other incrementally. You will start by creating a basic Bicep template to get you familiar with the tools & syntax. Then you extend your template incrementally to deploy multiple infrastructure resources to Azure.

### Challenges

- Challenge 0: **[Pre-Requisites - Ready, Set, Go!](./Student/Bicep-Challenge-00.md)**
   - Prepare your workstation to work with Azure
  
## Prerequisites

[Pre-Requisites - Ready, Set, Go!](./Student/Bicep-Challenge-00.md)

**NOTE:** These can take approx 30mins if you have updates to carry out so please allow time for this before starting other challenges

## Repository Contents 
- `../Student`
  - Bicep challenges
- `../Student/Resources`
  - Shell scripts needed to complete the challenges


