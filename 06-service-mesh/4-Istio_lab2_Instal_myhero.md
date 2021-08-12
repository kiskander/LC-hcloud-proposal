# Deploy the MyHero application and apply Istio policies

There are few steps you need to complete in order to install your application.

1. Create a `myhero` namespace and enable Istio
2. `git clone` the application and Istio manifest files
3. Identify the Istio system `ingressgateway` IP address
4. Update the manifests with the `ingressgateway` IP address
5. Deploy the `myhero` app and test it

## Creating the MyHero namespace
You need to create a namespace named `myhero` into which the application will be deployed. You also need to enable Istio in the namespace, which will ensure all of the pods that are deployed get an associated Istio sidecar.

To complete this task, you will use the Kubernetes CLI, `kubectl`.

1. Create a new name on your Kubernetes cluster:
    ```bash
    kubectl create namespace myhero
    ```

2. Enable Istio within that namespace:
    ```bash
    kubectl label namespace myhero istio-injection=enabled
    ```

3. Check Istio is enabled for the `myhero` namespace:
    ```bash
    kubectl get namespace -L istio-injection
    ```
## Find the Istio ingressgateway IP address

Istio automatically installs a number of components at installation. One of these components is an `ingressgateway`, which has an external IP address assigned to it. You will use this gateway IP for your application external communications. To find the `ingressgateway` IP address issue the following command:

```bash
kubectl -n istio-system get svc istio-ingressgateway
```

![alt text][kubectl_get_istio_gateway_ip]

[kubectl_get_istio_gateway_ip]: Istio_DNE_Images/kubectl_get_istio_gateway_ip.png

## Create MyHero manifests
All application and service deployments are made using manifest files. These files define your application and associated components. All the manifests you need to complete the labs in this module are stored in the [containers-code repository on GitHub](https://github.com/CiscoDevNet/containers-code). You need to clone the repo to your machine.

```bash
git clone https://github.com/CiscoDevNet/containers-code.git
cd ~/containers-code/module08/Istio_DNE_Manifiests/myhero_Templates
```

You will now have all the manifest files you need.
Some of the the manifests are currently `.template` files as you need to provide an IP address.

You need to update your Istio and Kubernetes manifests with this IP address and **once edited you need to save them as `.yml` files**.

The files that need editing are located in the `myhero_Templates` folder:

`istio_myhero_app_rule.template`<br>
`istio_myhero_gateway.template`<br>
`istio_myhero_ui_rule.template`<br>
`k8s_myhero_ui.template`<br>

To edit the files use your preferred text editor.
The example below uses [Atom](https://atom.io/).

![alt text][Istio-manifest-edit-example]

[Istio-manifest-edit-example]:Istio_DNE_Images/Istio-manifest-edit-example.png

Replace `<Istio-ingressgateway-IP>` on **all FOUR** manifest files above with the IP address that you recorded in the previous step. Please note that the `k8s_myhero_ui.template` manifest file has 3 instances of `<Istio-ingressgateway-IP>`.

For example, `app.<istio-ingressgateway-IP>xip.io` becomes `app.10.10.20.208.xip.io`.

(Note that you are using an [external DNS service xip.io](http://xip.io/) to mitigate some Sandbox nuances.)

***Don't forget to SAVE all FOUR of your updated manifest files with the `.yml` extension.***

## Deploy the app
So now that you have all your manifest updated you can deploy the app. First you start by deploying the _Istio services_ as follows.
```bash
kubectl -n myhero apply -f istio_myhero_app_rule.yml
kubectl -n myhero apply -f istio_myhero_ui_rule.yml
kubectl -n myhero apply -f istio_myhero_gateway.yml
```

Once all three _Istio services_ are up and running you deploy the `myhero` app manifests as follows.

```bash
kubectl -n myhero apply -f k8s_myhero_app.yml
```
```bash
kubectl -n myhero apply -f k8s_myhero_data.yml
```
```bash
kubectl -n myhero apply -f k8s_myhero_ui.yml
```

If you want, you can also deploy via the K8s dashboard, as shown below. **If you do so, PLEASE make sure that you have the `myhero` namespace selected before uploading the files.**

![alt text][k8s_dash_create]

[k8s_dash_create]:Istio_DNE_Images/k8s_dash_create.png

If you now take a look at the new pods, you will immediately notice that they include 2 containers, instead of just 1 as before (`READY 2/2`):

```bash
kubectl -n myhero get pods
```

You will be able to access `myhero` public IP address from your own browser and see the application working. Those new sidecar proxy containers that are intercepting all I/O are transparent to the service. You should be able to see the following screen.

**Note**: Your `myhero` public IP address will be something like `ui.<istio-ingressgateway-IP>xip.io`, where `<istio-ingressgateway-IP>` is the istio `ingressgateway` IP that you recorded above and used in all of your four updated manifest files.

![alt text][myhero_working]

[myhero_working]:Istio_DNE_Images/myhero_working.png

Vote for your favorite superhero to check the backend is working. After voting on your favorite super hero, your screen should update as shown below.

![alt text][myhero_backend]

[myhero_backend]:Istio_DNE_Images/myhero_backend.png

**Next: Control traffic routing and responses with Istio**
