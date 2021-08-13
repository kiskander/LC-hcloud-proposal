# Access the Terraform Workspace

Terraform workspaces enable you to collect the activities of infrastructure management into one place. This Learning Lab manages one workspace that references the Terraform elements that successfully provision VMs to vSphere.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist08.png?raw=true)

## Open the workspace and configure VM variables

Select __vmworkspace__. 

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist09.png?raw=true)

Click __Configure Variables__.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist10.png?raw=true)

You can change the following variables: 
* Number of VMs (`vm_count`)
* Number of CPUs per VM (`vm_cpu`)
* RAM allocated to each CPU (`vm_memory`). 

Click on the three dots to the right of each variable and choose __Edit__ to change the value.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist11.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist12.png?raw=true)

**Next: Run the Terraform Plan**
