# Execute TFCB plan to create an IKS cluster

In this exercise, you assume a DevOps persona to provision an IKS cluster. 

> *Note:* In a real-world scenario, app developer team requirements drive the IKS cluster profile. The DevNet Sandbox is a resource-constrained environment; for this Lab, you create a cluster with minimal resources.

## Queue the plan

Open the `sb_iks-XXXX` workspace in TFCB. Confirm that the variables are correct for the `api_key`, `secretkey`, and `mgmtcfgsshkeys`. Click **Queue plan manually** to execute the plan to create the IKS cluster.

![](assets/images/Picture13.png)

## Review and confirm the plan

The TFCB formulates a plan. Review the plan and verify the provisioning of the IKS cluster with the policies that you configured.

Confirm the plan to apply it to your infrastructure. **Provisioning can take as long as 30 minutes**.

On a successful run, you see a dump of the kubeconfig for the cluster that you created. You will use the kubeconfig in the next exercise to deploy a sample app. 

![](assets/images/Picture21.png)

## Verify the configuration

Log in to Intersight and verify the cluster configuration:

![](assets/images/Picture22.png)

An app developer can now deploy their containerized apps on the IKS cluster.

**Execute TFCB plan to deploy a sample app on the IKS cluster**
