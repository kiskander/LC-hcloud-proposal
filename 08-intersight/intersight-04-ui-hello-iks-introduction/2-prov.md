# Use Intersight UI to provision IKS profile for you IKS cluster

Next, you will provision an IKS Profile. This defines the IKS cluster that you want to create:

![](assets/images/main.png)

__1.__ Configure IKS General Info 

Intersight is Multi-Tenant and supports different organizations but for this Sandbox, select the default organization.

![](assets/images/gen.png)

__2.__: Configure IKS Cluster - Select IP Pool 

This IP Pool will be used for the Loadbalancer Services that we shall create at a later stage. These IP's will be assisgned to the application running on the IKS cluster.

![](assets/images/cluster.png)

__3.__: Configure IKS Cluster - Select Node OS Policy 

This policy gets mapped under the DNS, NTP and Timezone section.

![](assets/images/cluster2.png)

__4.__: Configure IKS Cluster - Select Network CIDR Policy 

![](assets/images/cluster3.png)

__5.__: Configure IKS Cluster - Configure Load Balancer Count and SSH key. 

Enter the SSH public key that you generated before.

![](assets/images/cluster4.png)

Click next, we won't configure any Trusted Registries or Container Runtime settings for now.

__6.__: Configure Control Plane Node Pool - Select Kubernetes Version

![](assets/images/ctrl.png)

__7.__: Configure Control Plane Node Pool - Select IPPool

These are the IP's which are getting assigned to the Control PLane VM's.

![](assets/images/ctrl2.png)

__8.__: Configure Control Plane Node Pool - Select Virtual Machine Infra Config Policy

![](assets/images/ctrl3.png)

__9.__: Configure Control Plane Node Pool - Select Virtual Machine Instance Policy

![](assets/images/ctrl4.png)

__10.__: Configure Control Plane Node Pool - Select Desired Size for Control Plane

The Min and Max size are for upgrades, the desired size is the amount of control VM's that will be provisioned.

![](assets/images/ctrl5.png)

__11.__: Configure Worker Node Pools - Select ippool, name and number of worker nodes

![](assets/images/worker.png)

__12.__: Configure Add-ons. You can skip this for now since we will address this in subsequent sections.

![](assets/images/add.png)

__13.__: Submit Cluster Provisioning Request

![](assets/images/summary.png)

__14.__: Verify Cluster Provisioning Request is Configuring

![](assets/images/config.png)

__15.__: Examine Cluster Provisioning Request Workflow

![](assets/images/workflow.png)

__16.__: Verify that the cluster is configured:

![](assets/images/connected.png)


Your App Developers can now deploy their containerized apps on the IKS cluster using kubectl or helm.