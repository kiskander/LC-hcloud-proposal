# Introducing Kubernetes

You should now understand why you need an orchestrator: so that you don't have to manually run containers in production, which would be nearly impossible at any scale.

![An Orchestrator gives us a single interface to a pool of resources](/posts/files/containers-intro-kubernetes/assets/images/orchestrator1.png)

## Choosing an Orchestrator
As with Virtual Machine orchestration, numerous solutions exist for orchestrating containers.

You have probably heard of some of the most common solutions:

* Docker Swarm / Docker Enterprise Edition (DockerEE)
* Apache Mesos & Marathon.
* Mesosphere DC/OS.
* Rancher
* Kubernetes

In this module, you will learn about Kubernetes.

## Why Kubernetes?
Kubernetes, an orchestrator initially developed and then donated to the open-source community by Google, is based on Google's internal "Borg" orchestrator, which was developed to manage Google data centers. Kubernetes been widely embraced by the open-source community.

![Kubernetes Contributions Github Top10 18](/posts/files/containers-intro-kubernetes/assets/images/githubk8s18.png)

Kubernetes has rapidly become the de facto container orchestrator, and is the most sensible choice for you to learn.

* Employers are more likely to seen out Kubernetes skills.
* The Kubernetes community offers plenty of help, support, and solutions to problems.
* The online training resources are first rate.

## A universal API for container management.

Such is the demand for Kubernetes that *every major cloud provider* offers managed Kubernetes. You can also run Kubernetes on your own hardware and in your own data centers. Kubernetes provides a universal API / Abstraction Layer for managing containers.

![Kubernetes Available Everywhere](/posts/files/containers-intro-kubernetes/assets/images/kuberneteseverywhere.png)

The widespread availability of Kubernetes makes it hugely powerful for multi- and hybrid cloud environments.

![Kubernetes Reduces MultiCloud Deployment Complexity](/posts/files/containers-intro-kubernetes/assets/images/kubernetesuniversal.png)


## Getting Kubernetes
Many cloud providers, both public and private, will provide a managed "Kubernetes as a Service" solution. However, you can also run a Kubernetes system locally. Managed Kubernetes services are convenient. However, remember that Kubernetes provides an abstraction layer, distancing developers and DevOps teams from the underlying infrastructure. Building your own from-scratch Kubernetes cluster will give you deeper insight into your container infrastructure.

The latest versions of Docker community edition come with a Kubernetes cluster built in, enabling you to try Kubernetes-style deployment on your local machine.

There are also web-based, "virtual environments" that enable you to interface with a Kubernetes cluster without touching your local environment. [Play With Kubernetes](https://labs.play-with-k8s.com/) is one of these services. A similar web-based interface is also available through Kubernetes documentation and training we'll be covering next.

## Deeper Reading
In this module, you will use Kubernetes to automate some container deployments. But those who really want to understand the internals of how Kubernetes operates can explore an excellent blog series called [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way).

![Kubernetes The Hard Way Complexity](/posts/files/containers-intro-kubernetes/assets/images/k8shardway.png)
