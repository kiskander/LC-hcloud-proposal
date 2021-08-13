# Introduction to Istio and service mesh

In this Learning Lab, you will learn the basics of using Istio service mesh on microservices, and understand why service mesh is useful.

![alt text][logo]

[logo]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Istio_banner.png?raw=true "Logo Title Text 2"


## Objectives

* Set up Kubernetes on a CentOS machine
* Install myhero Application
* Learn about Istio traffic routing
* Learn about Istio gradual migration
* Learn about Istio delay injection
* Learn about Istio HTTP abort injection

## Prerequisites
Before you attempt this Learning Lab, you should have completed all of the previous modules in the [Containers Learning Labs track](https://developer.cisco.com/learning/tracks/containers), including [Introduction to Container Management](https://developer.cisco.com/learning/modules/containers-mgmt) and [Introductions to Cisco Container Platform](https://developer.cisco.com/learning/modules/containers-ccp).

## A Brief History of microservices and the service mesh

In the "olden days", services such as routing, traffic management, load balancing, and security were delivered by discrete hardware or software appliances. In most cases, applications would leverage these services as traffic flowed across the network.

![alt text][Service_Mesh_olddays]

[Service_Mesh_olddays]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Service_Mesh_olddays.png?raw=true "Olden_Days"

Many of today's modern applications are container-based, built as microservices, and typically deployed on container orchestrators like Kubernetes. The old way of delivering services to apps no longer works or scales for modern hardware and software stacks.

![alt text][Service_Mesh_missinglayer1]

[Service_Mesh_missinglayer1]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Service_Mesh_missinglayer1.png?raw=true "Missing_Layer"

A microservices architecture differs from other architectures in that individual microservices are built independently, are loosely coupled, and communicate with each other to provide the overall service/application.

The logic governing communication between services can be coded into each service but it can quickly become complex and an overhead for the developer.

A **service mesh** is an abstraction that takes the logic of service-to-service communication away from individual services and abstracts it to a layer of infrastructure.

![alt text][Service_Mesh_Istio]

[Service_Mesh_Istio]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Service_Mesh_Istio.png?raw=true "ISTIO"

There are a number of service mesh solutions in the market. The current leader is Istio, an open-source project from Google. Istio is an open, platform-independent service mesh that supports Kubernetes.

![alt text][Service_Mesh_Istio_Services]

[Service_Mesh_Istio_Services]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Service_Mesh_Istio_Services.png?raw=true "ISTIO"

Istio makes it easy to create a network of deployed services. You add Istio support to services by deploying a special sidecar proxy throughout your environment. The proxy intercepts all network communication between microservices, then configures and manages Istio with its control plane functionality, which includes:

* Fine-grained control of traffic behavior
* Automatic load balancing
* Automatic metrics, logs, and traces
* Secure service-to-service communication

Istio includes the following components.

* **Pilot**: Used for Traffic Management
* **Envoy Proxy**: The sidecar High Performance Proxy.
* **Mixer**: Delivers Policy and Telemetry
* **Citadel**: Provides Identity and Credential Management

![alt text][Service_Mesh_Istio_Architecture]

[Service_Mesh_Istio_Architecture]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Service_Mesh_Istio_Architecture.png?raw=true "ISTIO"

You can learn more about Istio in the [Istio documentation](https://istio.io/docs/concepts/what-is-istio/).
