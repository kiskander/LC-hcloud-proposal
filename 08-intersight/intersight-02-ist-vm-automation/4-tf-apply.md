# Run the Terraform Apply

Now that you are satisfied with the plan, you can apply your changes and provision the VMs to vSphere.

## Apply the Plan

Back in Terraform Cloud, open the __Runs__ tab. Scroll to the bottom of the completed plan. Click __Confirm and Apply__.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist19.png?raw=true)

If the apply is successfully queued, you see the following confirmation:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist20.png?raw=true)

Another confirmation shows that the apply is in progress:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist21.png?raw=true)

Return to to [vSphere](http:10.10.20.131) and observe the VMs that vSphere creates based on your configured variables.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist22.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist23.png?raw=true)

Once the apply is complete, Terraform Cloud returns a message indicating success:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist24.png?raw=true)

Now that you have completed this Learning Lab, end your reservation by clicking the **End reservation** button in the [Sandbox](https://devnetsandbox.cisco.com/RM/Diagram/Index/0e9e018d-3c2f-4bc8-acd9-1caa1ef81a48). Doing so releases the Sandbox and resets it for the next user.

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-02-ist-vm-automation/assets/images/ist26.png?raw=true)

**Congratulations! You've completed the Intersight Service for Terraform VM Provisioning Lab.**
