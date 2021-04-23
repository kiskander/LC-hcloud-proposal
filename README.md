# Cisco Hybrid Cloud Content Breadboarding


## What's The Problem?
Cisco's Hybrid Cloud is catchy and feasible given the latest product releases, investment and partnership with key players in the cloud orchestration vertical. The problem is the story is being told with no learning content to allow Cisco learning Community (external and internal) to learn how to construct their hybrid cloud , up skill their workforce into a true DevOps operation and grow Engineer of The Future.
We should build content around Public and Private Cloud that clearly explains, differentiates and teach the implementation of both cloud instances


## What's Needed ?
New Learning content built to walk through the journey. Curriculum that is tailored for both Developers and Network Engineers. The expectation is to spend time curating new content and deliver it in a fresh, interactive, relevant and fun way. Proposed content to be released within 2-3 Months in batches. 
- Content to be interactive 
- Cross Platform integration to focus on API utilization 
- Third party open source tooling should be incorporated as part of the learning process
- Content to tell the use case from soup to nuts
- Content to be built in a modular format to resonate to different DevOps personas (Dev, SRE, Ops)


## Cisco Hybrid Cloud Vade Mecum

![overview](assets/img.png)

There are multilayers to understanding and learning Cloud infrastructure and deployment. the purpose of this learning course is to put the puzzle pieces together, allow our learning community to deep dive into the important pieces and place it together to see the bigger picture.

The course is designed to deliver the information in pieces and to keep building on top of the foundation. Think building a lego model. Start small and finish big.

**Compare and contrast Private cloud and Public cloud** Before we start deep diving onto the technologies in this course it would make sense to teach some of the concepts involved: what is public cloud? what is private cloud? which components are important to run your application on each. this is the foundation we will start building on top

**Introduction to Git, Gitlab, CICD** Part of allowing teams to communicate better is to teach them similar lingo, in this case we want to allow the Dev team , SRE and OPs to understand the lifecycle of app development and deployment. Bringing in Git and teaching the Devops methodologies is an important concept that will help tie the puzzle together. 

**Introduction to Containers** You need containers app development is micro services in this part of the course we should cover containers, how to build them, configure them and deployment them. this will tie in to the preview topic of CICD 

**Introduction to Kubernetes** Now that we understand containers, how do we apply orchestration to containers? this section will give us a deep dive onto kubernetes. It's important to have a Kubernetes deployed somewhere so students can get hands on with `kubectl` 

**Introduction to DNS Global Site Load Balancing** One concept that needs to be taught that's important in the hybrid cloud world is DNSGSL, how do you tell traffic to go where when you have have redundant deployment of your application. DNS Global Site load balance like Hashicrop Console or something similar can be a focus here. 

**Getting Started with Terraform** This section of the course is a big topic area that should be focused on. Terraform allows for seamless deployment of hybrid cloud. When talking about Terraform we need to focus on the HCL as a language, teach the syntax as well as the usability of Terraform + configuration. This should be a hands on , follow the instructor kind of low code session. we should also touch on how this ties in with Cisco and its products as it will be a good segway into the next topics 

## Content
#### Course Core
* Compare and contrast Private cloud and Public cloud `|Dev|SRE|OPS|`
* Introduction to Git, Gitlab, CICD `|Dev|SRE|OPS|`
* Introduction to Containers `|Dev|SRE|OPS|`
* Introduction to Kubernetes `|Dev|SRE|OPS|`
* Introduction to DNS Global Site Load Balancing (Hashi Console?)
* Getting Started with Terraform
* Deep dive into Private Cloud components 
   	- Cisco Intersight
   	- Cloud OnRamp with SDWAN (vMX)
   	- Intersight Assist
   	- Intersight Kubernetes Service (IKS)
   	- Intersight workflow optimizer (IWO)
   	- Terraform and Cisco Intersight
* Deep dive into Public Cloud components (AWS focused)
	-  Getting started with AWS (Tools, SDKs, CLI)
	-  Elastic Kubernetes Cluster
	-  Virtual Private Cloud 
	-  Security and IAM

#### Course Optional Module - DataCenter Networking
`This content should be present part of CCNP Data Center course`

* ACI Deployment and Config
* ACI Anywhere (Cloud APIC)

#### Course optional Module - DataCenter Compute
`This content should be present part of CCNP Data Center Core course`

* UCS Deployment
* Understanding UCS Manager B series vs UCS Manager with HX
* Building service templates 
* Understand HX and deployment capabilities  

#### Course optional Module - Networking
`This content should be present part of CCNP Networking course`

* Network deployment and Architecture 
* Routing/Switching
* Network Architecture designs  


## Rabbit Holes
Providing access to public cloud 



## No Goes