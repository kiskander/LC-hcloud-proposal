# Login to Terraform Cloud

This exercise introduces the preprovisioned entities in the Terraform Cloud.

## Accept the Terraform Cloud Invitation

When you reserve the Sandbox, you receive an invitation in your email to log in to Terraform Cloud for Business.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-03-ist-hello-iks-introduction/assets/images/Picture6.png?raw=true)

Click **Accept Invitation** and enter the same address at which you received the email and choose a password. Log into the TFCB portal at https://app.terraform.io.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-03-ist-hello-iks-introduction/assets/images/Picture7.png?raw=true)

Click **Accept** for CiscoDevNet. You see a list of workspaces.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-03-ist-hello-iks-introduction/assets/images/Picture8.png?raw=true)

## Examine Terraform Cloud preprovisioned resources

At this point, you see the following preprovisioned workspaces that are automatically linked to a CiscoDevNet VCS repo:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-03-ist-hello-iks-introduction/assets/images/Picture9.png?raw=true)

Refer to the following list for more information about the workspaces, including the linked GitHub repository and execution modes.

| Workspace            | Description                                                                       | Execution mode | GitHub repository                              |
|----------------------|-----------------------------------------------------------------------------------|----------------|------------------------------------------------|
| `sb_globalvar_xxxx`  | Sets up the variables for the rest of the workspaces                              | Remote         | https://github.com/CiscoDevNet/tfglobalvar.git        |
| `sb_k8sprofile_xxxx` | Sets up the Terraform configuration to provision IKS profiles                     | Remote         | https://github.com/CiscoDevNet/tfk8spolicy.git        |
| `sb_iks_xxxx`        | Sets up the Terraform configuration to provision the IKS cluster                  | Remote         | https://github.com/CiscoDevNet/intersight-tfb-iks.git |
| `sb_iksapp_xxxx`     | Sets up the Terraform configuration to deploy a sample app using Helm TF Provider | Agent          | https://github.com/CiscoDevNet/tfiksapp.git           |
| `sb_iksdelete_xxxx`  | Deletes the IKS profile and cluster                                               |                | https://github.com/CiscoDevNet/tfiksdelete.git        |

There are two kinds of execution modes:

* **Agent**: The Helm deployment of a sample app on the k8s cluster, using the Terraform Cloud agent in the remote datacenter. 
* **Remote**: The Terraform SAAS calls on the Intersight Terraform Provider to provision the policies and to provision and deprovision the IKS cluster.

**Next: Log in to Intersight**
