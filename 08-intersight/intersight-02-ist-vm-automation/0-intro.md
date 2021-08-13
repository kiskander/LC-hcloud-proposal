# Introduction

This Lab introduces the elements and processes for provisioning virtual machines with the Intersight Service for Terraform.

## Objectives

When you complete this Learning Lab, you will be familiar with:

* Interactivity of Terraform Cloud with Intersight, Intersight+Terraform Assist, and Intersight+Terraform Cloud Agent.
* Accessing Terraform Cloud and observing Terraform workspaces.
* Changing infrastructure-related variables to inform Terraform plan and apply.
* Initiating a Terraform plan for virtual machine creation in VMWare vSphere.
* Initiating a Terraform apply for virtual machine creation in VMWare vSphere.

## Prerequisites

Before you begin, complete [Introduction to Intersight Service for Hashicorp Terraform](https://developer.cisco.com/learning/lab/intersight-01-ist-introduction/step/1.

To complete this Learning Lab, you need a reservation at the [Intersight Service for Hashicorp Terraform Sandbox](https://devnetsandbox.cisco.com/RM/Diagram/Index/055e2dce-fdfd-4d26-a112-72b884ddd7c7?diagramType=Topology)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-01-ist-introduction/assets/images/ist02.png?raw=true)

When the reservation process is complete, you receive an email that contains VPN credentials.  

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-01-ist-introduction/assets/images/ist16.png?raw=true)

Follow those instructions to connect to the VPN. Complete this task to access the vSphere instance later.

### Pre-configured elements of the Intersight Service for Hashicorp Terraform Sandbox

For a consistent experience, the Sandbox contains the following pre-configured elements:

* Intersight
* Terraform Cloud Business and workspace
* Terraform Cloud Agent
* Intersight+Terraform Cloud Assist
* VMWare vSphere

Intersight is Cisco's cloud-based infrastructure management platform. Terraform Cloud Business is the SaaS deployment of Terraform. In the DevNet Sandbox, you load the Terraform files for your provisioning plan (available at [https://github.com/CiscoDevNet/vm-intersight-terraform](https://github.com/CiscoDevNet/vm-intersight-terraform)) and track the success or failure of your deployment.

VMWare vSphere is the hypervisor that manages the VMs that you create.

## Workflow

This diagram shows how the components for this Learning Lab fit together.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-01-ist-introduction/assets/images/ist25.png?raw=true)


**Next: Log in to Terraform Cloud for Business and observe workspaces**
