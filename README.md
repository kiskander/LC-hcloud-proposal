# Cisco Hybrid Cloud Content Breadboarding


Cisco's Hybrid Cloud is about enabling Cisco customers to create extraordinary experiences by fusing the best of cloud and on-premises. Some things to keep in mind:

* Every cloud is different, and every cloud strategy is different, with customers embracing cloud in unique ways. Organizations are accelerating their cloud journey across a spectrum of motions with their main goal providing digital experiences to their users better and faster.
* The new reality is a hyper-distributed, extremely diverse IT landscape with multiple locations, remote teams and users...and across this landscape, there is one constant: change. As organizations are aiming to minimize risk while converging the existing “traditional IT” with “cloud-first” or “cloud-inspired”, the challenge is not to evolve now, but to be adaptive...always.
* Across every layer of the digital experience, customers need a cloud-neutral operating model with full-stack observability and automation to accelerate and make their clouds work smarter while maintaining control and choice.


*Personas*: 

Need: 
DevOps Engineers working on defining and deploying Cisco's Hybrid Cloud solutions are faced with the need to know very specialized information. Within the DevOps group emerge three personas that we can target with specific learning opportunities.

1) Developers whose focus is application planning, design and deployment. 
2) Site Reliability Engineers who are tasked with efficiently managing systems, solving problems, and automating operations that cater for developer's needs
3) Operation teams who architect and build infrastructure to allow for it all.

*Current State*: 

With the DevOps Engineering role growing in the market, our customers need the ability to learn and understand Cisco's product offerings that pertain to our Hybrid Cloud story. 

Challenge 1: Cisco Cloud learning content is currently tailored to a specific persona and focused on a single Cisco product. There is no course around the entire hybrid cloud use case to answer questions like "How does Hashicorp Terraform work and why do I care about it? - from a Cisco Perspective" or "Why should I care about Kubernetes?" 
 
Challenge 2: It is also challenging to build content that is relevant to different audiences within DevOps roles. This has to be kept in mind while building this course content. 


## What's Needed?
New learning content built to walk through the entire hybrid cloud journey delivered in a fresh, interactive, relevant and fun way. Proposed content to be released within 2-3 months in batches. 

* Content to be interactive 
* Cross Platform integration to focus on API utilization 
* Third party open source tooling should be incorporated as part of the learning process
* Content to tell the use case from soup to nuts
* Content to be built in a modular format to resonate to different DevOps personas (Dev, SRE, Ops)
* Check points and Badges incorporated
* Cisco Certification Exam topics to course content mapping
* Create a content journey for beginners, intermediate and advanced learners


## Cisco Hybrid Cloud Vade Mecum

![overview](assets/img.png)

There are multiple layers to understanding and learning Cloud infrastructure and deployment. The purpose of this learning course is to put the puzzle pieces together, allow our learning community to deep dive into the important pieces and place them together to see the bigger picture.

The course is designed to deliver the information in pieces and to keep building on top of the foundation. Think building a Lego model. Start small and finish big.

**Compare and contrast Private cloud and Public cloud** Before we start deep diving onto the technologies in this course it would make sense to teach some of the concepts involved: what is public cloud? what is private cloud? which components are important to run your application on each. This is the foundation we will start building on top of.

**Introduction to Git, Gitlab, CICD** Part of allowing teams to communicate better is to teach them similar lingo, in this case we want to allow the Dev team , SRE and OPs to understand the lifecycle of app development and deployment. Bringing in Git and teaching the Devops methodologies is an important concept that will help tie the puzzle together. 

**Introduction to Containers** In part of the course, we’ll take a look at what containers are, how they are different from other kinds of virtualization technologies, and what advantages they can offer for your development and operations processes. There should be a hands-on portion on how to build them, configure them and deployment them. this will tie into the preview topic of CICD 

**Introduction to Kubernetes** Now that we understand containers, how do we apply container orchestration and management? This section will give us a deep dive into Kubernetes.What is it? And how does it work? It's important to have a Kubernetes deployed somewhere so learners can get hands on with `kubectl` 

**Introduction to DNS Global Site Load Balancing** One concept that needs to be taught that's important in the hybrid cloud world is DNSGSL, how do you tell traffic to go where when you have redundant deployment of your application? DNS Global Site load balance like Hashicrop Console or something similar can be a focus here. 

**Getting Started with Terraform** This section of the course is a big topic area that should be focused on. Terraform allows for seamless deployment of hybrid cloud. When talking about Terraform we need to focus on the HCL as a language, teach the syntax as well as the usability of Terraform + configuration. This should be a hands on , follow the instructor kind of low code session. we should also touch on how this ties in with Cisco and its products as it will be a good segue into the next topics 

**Deep dive into Private Cloud components** Here is where Cisco is a key player in hybrid cloud. This is where we start talking about Intersight and its features. this portion of the course should focus on topics like: What is Intersight (Tour du Monde), Why is it a key player in cloud Orchestration? 
We then deep dive on the key features of Intersight that allows for hybrid cloud integration things like Intersight Assist, IKS .. etc  Deep diving into this content should cover deployment, configuration. 

**Deep dive into Public Cloud components (AWS focused)** Although this is not Cisco, Public cloud providers is considered an integration point with Cisco Intersight, therefor it is important to talk about the different components that are at play from a Public cloud perspective. Understand EKS for example, VPC configuration to allow traffic between the different cloud instances and Security. This can easily be consumed from third party content creators and leveraged as part of this course 

## Content
**Personas** - `|Dev|SRE|OPS|` 

**Platforms** - (C)isco vs (T)hird Party (Udemy, Codeacademy ...etc) 
#### Course Core
* Compare and contrast Private cloud and Public cloud `|Dev|SRE|OPS|` (C)(T)
* Introduction to Git, Gitlab, CICD `|Dev|SRE|OPS|` (C)(T)
* Introduction to Containers `|Dev|SRE|OPS|` (C)(T)
* Introduction to Kubernetes `|Dev|SRE|OPS|` (C)(T)
* Introduction to DNS Global Site Load Balancing (Hashicorp Console?) `|Dev|SRE|OPS|` (C)(T)
* Getting Started with Terraform `|Dev|SRE|OPS|` (C)(T)
* Deep dive into Private Cloud components `SRE|OPS|` (C)
   	- Cisco Intersight `|SRE|OPS|` (C)
   	- Intersight Assist `|OPS|` (C)
   	- Intersight Kubernetes Service (IKS) `|OPS|` (C)
   	- Intersight workflow optimizer (IWO) `|SRE|OPS|` (C)
   	- Terraform and Cisco Intersight `|SRE|OPS|` (C)
   	- Cloud OnRamp with SDWAN (vMX) `|OPS|` (C)
   	- Container Security with PortShift `|OPS|` (C)
* Deep dive into Public Cloud components (AWS focused)
	-  Getting started with AWS (Tools, SDKs, CLI)  `|Dev|SRE|OPS|`  (C)(T)
	-  Elastic Kubernetes Cluster `|Dev|SRE|OPS|` (C)(T)
	-  Virtual Private Cloud `|Dev|SRE|OPS|` (C)(T)
	-  Security and IAM `|Dev|SRE|OPS|` (C)(T)
	


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
* Is the platform ready for hands on experience portion of the content?
* Do we have BU alignment with product content?
* Are the Content creators knowledgeable of topic at hand?
* Does similar content exist somewhere else?
* Staying up to date with the product releases and updating content accordingly



## No Goes
The platform has to support a seamless integration with the content offering. Having our learners jump around different screens and windows to get a hands on experience is a deal breaker for delivering this course content. 
