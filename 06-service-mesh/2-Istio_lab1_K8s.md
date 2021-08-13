# Configure your Kubernetes environment for Istio

In this exercise, you will set up the Kubernetes command line tool `kubectl` on a CENTOS machine

The Kubernetes command-line tool, `kubectl`, allows you to run commands against Kubernetes clusters. You can use `kubectl` to deploy applications, inspect and manage cluster resources, and view logs.

[We created a K8s cluster in the Introduction to Cisco Container Platform module](https://developer.cisco.com/learning/tracks/containers/container-containers-ccp/containers-ccp-create-k8s-cluster/step/3) called __API-Cluster-1__. To install our application on this cluster we will use `kubectl`.

`kubectl` gives us an alternative configuration option to the Dashboard and API we saw in the previous modules. `kubectl` is especially useful as it allows you to switch between multiple k8s clusters under your control from your host or laptop. First we need to setup the CentOS machine with the appropriate `kubectl` credentials so it can connect to the our cluster.

So, our next step is to setup `kubectl` on the CENTOS machine to remotely control the cluster from your computer.

## Setup Kubectl on your computer to remotely control the cluster from CLI
From the CentOS machine open a terminal window. (username: _developer_ password: _C1sco12345_). `kubectl` should already be installed on your machine.

Take a look at your Kubernetes CLI current configuration by running:

```bash
kubectl config view
```

![alt text][kubectl_config_view_3]

[kubectl_config_view_3]:https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/kubectl_config_view_3.png?raw=true "Config View"

The output from this command shows that our `kubectl` configuration file is empty and not pointing to any k8s clusters.

`kubectl` leverages a `kubeconfig` file that is used to configure access to k8s cluster(s). This file typically lives at `$HOME/.kube/config`

There are three ways to point your `kubectl` to a `kubeconfig`. These are listed in the order of preference that takes effect when `kubectl` is determining which `kubeconfig` file  to use:

* `--kubeconfig` flag, if specified
* use `KUBECONFIG` environment variable, if specified
* `$HOME/.kube/config` file

For this exercise, you will use the environment variable option.

`kubectl` also uses the `kubeconfig` file to point to the correct cluster(s). In the CCP module you downloaded the `kubeconfig` for clusters "Sandbox-Demo-Cluster-1" and UI-Cluster (`kubeconfig.yaml` and `kubeconfig (1).yaml`) to access the Kubernetes Dashboard using a browser.

The kubeconfig file(s) from the previous modules should be located in the downloads directory. You need to __DELETE__ this before downloading the `kubeconfig` for API-Cluster-1.

 ![alt text][Delete_Kubeconfig]

[Delete_Kubeconfig]:https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/kubectl_delete_old_kubeconfig1.png?raw=true "KUBECONFIG"


Next, go to the CCP UI (https://198.18.1.110, username `admin` and password `Cisco123`)and download the new `kubeconfig` for API Cluster-1.

![alt text][Kubeconfig_download]

[Kubeconfig_download]:https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/Kubectl_download_kubeconfig_from_ccp.png?raw=true "KUBECONFIG"

On the CENTOS machine command line, issue the following commands to point `kubectl` to the API-Cluster-1 `kubeconfig`.

```bash
echo $HOME
echo $HOME/Downloads
export KUBECONFIG=$HOME/Downloads/kubeconfig.yaml
```

![alt text][Kubectl_switch_context]

[Kubectl_switch_context]:https://github.com/kiskander/LC-hcloud-proposal/blob/main/06-service-mesh/Istio_DNE_Images/kubeconfigENV1.png?raw=true "Config View"

With `kubectl` now using the new API-Cluster-1 `kubeconfig`, you should now be able to view and control the API-cluster-1 form the CLI.

```bash
`kubectl` get nodes
```

You should now see the nodes of the remote cluster.

Well done. Your work here is done!

**Next: MyHero: A microservices application**
