# Use Intersight UI to provision IKS profile for you IKS cluster

Next, you will provision an IKS Profile. This defines the IKS cluster that you want to create:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/main.png?raw=true)

__1.__ Configure IKS General Info 

Intersight is Multi-Tenant and supports different organizations but for this Sandbox, select the default organization.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/gen.png?raw=true)

__2.__: Configure IKS Cluster - Select IP Pool 

This IP Pool will be used for the Loadbalancer Services that we shall create at a later stage. These IP's will be assisgned to the application running on the IKS cluster.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/cluster.png?raw=true)

__3.__: Configure IKS Cluster - Select Node OS Policy 

This policy gets mapped under the DNS, NTP and Timezone section.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/cluster2.png?raw=true)

__4.__: Configure IKS Cluster - Select Network CIDR Policy 

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/cluster3.png?raw=true)

__5.__: Configure IKS Cluster - Configure Load Balancer Count and SSH key. 

Enter the SSH public key that you generated before.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/cluster4.png?raw=true)

Click next, we won't configure any Trusted Registries or Container Runtime settings for now.

__6.__: Configure Control Plane Node Pool - Select Kubernetes Version

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrl.png?raw=true)

__7.__: Configure Control Plane Node Pool - Select IPPool

These are the IP's which are getting assigned to the Control PLane VM's.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrl2.png?raw=true)

__8.__: Configure Control Plane Node Pool - Select Virtual Machine Infra Config Policy

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrl3.png?raw=true)

__9.__: Configure Control Plane Node Pool - Select Virtual Machine Instance Policy

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrl4.png?raw=true)

__10.__: Configure Control Plane Node Pool - Select Desired Size for Control Plane

The Min and Max size are for upgrades, the desired size is the amount of control VM's that will be provisioned.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ctrl5.png?raw=true)

__11.__: Configure Worker Node Pools - Select ippool, name and number of worker nodes

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/worker.png?raw=true)

__12.__: Configure Add-ons. You can skip this for now since we will address this in subsequent sections.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/add.png?raw=true)

__13.__: Submit Cluster Provisioning Request

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/summary.png?raw=true)

__14.__: Verify Cluster Provisioning Request is Configuring

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/config.png?raw=true)

__15.__: Examine Cluster Provisioning Request Workflow

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/workflow.png?raw=true)

__16.__: Verify that the cluster is configured:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/connected.png?raw=true)


Your App Developers can now deploy their containerized apps on the IKS cluster using kubectl or helm.