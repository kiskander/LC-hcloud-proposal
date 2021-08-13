# MyHero application architecture

In order to demonstrate the power of Istio, you will install a microservices applications called `myhero`. You will then learn how Istio can be used to manage traffic to and from different microservices.

`myhero` is a simple app that enables you to vote for your favorite superhero. It is made of three services: *Presentation_, *APP* and *Data*. Each service communicates via API.

![alt text][myhero_1]

[myhero_1]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/myhero_1.png?raw=true "MyHero"

Each service is defined by a manifest file. When deployed onto the kubernetes(Kubernetes) cluster the *Data* and *APP* services use one pod each and the *Presentation* service uses three pods.

![alt text][myhero_2]

[myhero_2]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/myhero_2.png?raw=true "MyHero2"

`myhero` could work happily leveraging the native Kubernetes networking and load balancing services. However, you want to add Istio as the service mesh abstraction, so you need another set of manifest files to get the app up and running.

![alt text][myhero_istio_1]

[myhero_istio_1]: https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/myhero_istio_1.png?raw=true "MyHero2"

When Istio is enabled within a Kubernetes namespace, it automatically installs a second container, the envoy proxy, or sidecar. This sidecar proxies all traffic in and out of the pod and, in doing so, it provides a policy control point.

In our initial `myhero` deployment, the Istio manifest files define the following traffic management services.

* A **Gateway** configures a load balancer for HTTP/TCP traffic, most commonly operating at the edge of the mesh to enable ingress traffic for an application.
* A **VirtualService** defines the rules that control the routing of requests for a service within an Istio service mesh.
* A **DestinationRule** configures the set of policies to be applied to a request after VirtualService routing has occurred.

With the Istio traffic management in place, you can now control traffic to and between your application services.

**Next: **
