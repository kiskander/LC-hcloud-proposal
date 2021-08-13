# Use Intersight UI to configure IKS Add-ons

__1.__: Connect to the Sandbox VPN with the credentials provided in your invitation email.

__2.__: Create a policy for the Dashboard Add-on:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/addonpol.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/addonpol2.png?raw=true)

__3.__: Update the cluster profile and include the Add-on policy. Leave the other fields empty and click **Deploy**:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/addonprof.png?raw=true)

__4.__: Connect to the control plane node of the cluster that you created

Get the Control plane node IP:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrlnode.png?raw=true)

Download the kubeconfig for the cluster.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/kube.png?raw=true)

Connect to control plane node with ssh. Use the private key that you generated before.

ssh -i <your_private_ssh_key> iksadmin@ctrlplanenode-ip

__5.__: Execute the following commands to get the data for the Dashboard access

Get the name of the default token:

    kubectl --kubeconfig <cluster-kubeconfig> get secrets -n kube-system | grep default-token

Get the password: 

    kubectl --kubeconfig <cluster-kubeconfig> get secret default-tokvv -n kube-system -o jsonpath='{.data.token}' | base64 -D

__6.__: Access the Kubernetes Dashboard for your cluster

Navigate to **Operate -> Kubernetes -> Select your cluster -> Operate -> Add-ons** and click on your Add-on. You should now see your Kubernetes Dashboard lited. You can login with the Token you got in the previous step.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/dashinv.png?raw=true)

Access the Dashboard and enter the token acquired above:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/xxx.png?raw=true)

Check out the cluster you just created with the Dashboard:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/dash.png?raw=true)


