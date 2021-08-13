# Introduction

This Lab walks you through the provisioning of an IKS cluster in Intersight using its UI and ClickOps. To automate the same with Intersight Service for Terraform, please refer to the following Learning Lab and Sandbox:

https://devnetsandbox.cisco.com/RM/Diagram/Index/daad55dd-45f1-46c6-a1b4-7339b318c970?diagramType=Topology

**Note**: For a successful tutorial, lab user will follow the instructions in this lab without modifying any other attributes or deleting any resources.

## Objectives

When you complete this Learning Lab, you will be familiar with:
*	Use Intersight UI to provision IP Pool
*   Use Intersight UI to provision IKS policies
*   Use Intersight UI to provision IKS cluster profiles
*   Use Intersight UI to configure IKS add-ons
*   Use Intersight UI to scale up the cluster
*   Use Intersight UI to undeploy IKS cluster
*   Use Intersight UI to delete IKS cluster profile
*   Use Intersight UI to delete IKS policies

## Audience
*	Cloud Admins who would like to provide IT Container As A Service (CAAS) on vSphere Infrastructure  
*	DevOps who would like to deploy and manage k8s clusters


## Related Technologies

### Kubernetes as a Container Orchestration Platform

Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.
One of the main tenets of Kubernetes is giving you the freedom to take advantage of on-premises, hybrid, or public cloud infrastructure, letting you effortlessly move workloads to where it matters to you.

While DevOps has successfully leveraged public clouds offerings of Kubernetes to host containerized workloads, IKS provides the platform to bring the same cloud experience on prem on your vSphere Infrastructure.

### Intersight Kubernetes Service - IKS

IKS is a SaaS-delivered, turn-key container management platform for multicloud, consistent production-grade Kubernetes. It:

*	Runs on ANY infrastructure as a lightweight self-hosted software. Optimized for Cisco HX and UCS, deployed on top of VMware vSphere, with other Hypervisors and bare metal options coming soon
*	Automates the deployment and lifecycle management (OS updates/Kubernetes updates) of 100% upstream self-service K8s clusters via an easy-to-use user interface
*	Includes all the necessary networking (Calico CNI, Istio Service mesh), persistent storage (vSphere CSI), monitoring (Prometheus/Grafana), L4/L7 load balancing, registry tooling and RBAC configuration
*	Integrates with AWS, Azure, and Google Cloud (coming soon)
*	Is built for the enterprise with hardened security and enhanced availability features like multiple control nodes and self-healing features
*	Optimized for AI/ML workloads with multi-GPU support

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/Picture2.png?raw=true)


## Prerequisites

*   Note the licensing requirement to use the Intersight Kubernetes Service in your own data center. You will need the Premier or Advantage license to be able to use IKS. The Sandbox has these licenses preprovisioned for Lab users and so there is nothing that you need to do to complete this Learning Lab.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/license.png?raw=true)

*   Make a reservation at the following IKS with UI & ClickOps Sandbox:

TBD - link to new SB?

*   Upon reservation, you will receive another email indicating access to VPN credentials.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/Picture4.png?raw=true)

*   Follow instructions in the invitaton email to connect to the sandbox VPN (this is necessary to access the vSphere, IKS cluster and App instance later.)

*   Generate SSH keys and make a note of the public and private keys and their locations. You will need this in the cluster provisioning and access steps below.

## Pre-configured elements (Sandbox Topology)

To make for a consistent experience, the following elements are pre-configured in the accompanying sandbox environment.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/Picture33.png?raw=true)

##### Lab user accounts in Intersight SAAS
Intersight is a SaaS-delivered, common platform for intelligent visualization, optimization, and orchestration for applications and infrastructure across hybrid cloud. You will be provided with a temporary account for the duration of this Sandbox. You will need this to execute some manual steps later in the lab.


##### UCS Emulator
Cisco UCS Platform Emulator is the Cisco UCS Manager application that is bundled into a virtual machine (VM). The VM includes software that emulates hardware communications for the Cisco Unified Computing System (Cisco UCS) hardware that is configured and managed by Cisco UCS Manager.

##### Intersight Assist
Cisco Intersight Assist helps you add endpoint devices to Cisco Intersight. A datacenter could have multiple devices that do not connect directly with Cisco Intersight. Any device that is supported by Cisco Intersight but does not connect directly with it needs a connection mechanism. Cisco Intersight Assist provides that connection mechanism, and helps you add devices into Cisco Intersight.

##### VMWare vSphere
This is the hypervisor managing the IKS cluster VM’s being created for k8s control plane and worker nodes.


## Login to Intersight

1. Log in to Intersight with the link provided in your invitation email. 

2. Examine pre-configured elements (Intersight Targets). The following targets are pre-configured in Intersight corresponding to the remote entities and agents that it integrates with. Ignore the Terraform related Targets, we will not be using those in this Learning Lab.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/Picture5.png?raw=true)

The above targets are required to account for Intersight's integrations with the on prem entities. 

**Note**: If the vSphere Target shows as **Not Connected**, try editing the Target and changing an attribute, such as the Datastore Enabled setting, and Save. If any of the Targets still shows as **Not Connected**, do not use the Sandbox - you can terminate yur current reservation and start another reservation. 
