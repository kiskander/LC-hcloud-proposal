# Log in to vSphere and Terraform Cloud for Business

In this exercise, you create VMs managed in VMWare vSphere by executing a Terraform plan that is managed and run by Terraform Cloud. Intersight acts as the act as the IaC proxy through the Intersight assist and Terraform agent, and provides a secure pipeline for deployment.

Before you begin, ensure that you have an active Sandbox reservation and have connected to it with VPN.

## Log in to vSphere

Navigate to [http://10.10.20.131](http://10.10.20.131) and click __Launch vSphere Client (HTML 5)__. Login with the username `developer@vsphere.local` and the password `C1sco!23`.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist17.png?raw=true)

Click the second menu item, which resembles two pieces of notepaper. Observe that NO VMs have been provisioned.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist18.png?raw=true)

## Accept the Terraform Cloud invitation

When you reserve the Sandbox, you also receive an invitation in your email to log in to [Terraform Cloud for Business](). You can access a preprovisioned workspace that is tied to the activities that follow.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist03.png?raw=true)

Click __Accept Invitation__ and enter the same address at which you received the email and choose a password.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist04.png?raw=true)

Choose __Accept__ for __CiscoDevNet__. You will see a list of workspaces.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist05.png?raw=true)

**Next: Access the Workspace**
