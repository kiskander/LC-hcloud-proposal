# Log in to Intersight

You are ready to log in to Intersight with the link from your Cisco DevNet Sandbox email. Refer to the **Intersight Access Details** section in the email for the URL, user name, and password.

## Examine pre-configured elements (Intersight Targets)

Intersight contains the following pre-configured targets that correspond to the remote entities and agents that it integrates with.

![](assets/images/Picture5.png)

These targets are required to account for Intersight's integrations with the on-premises agents and TFCB.

NOTE: At times, the vSphere Target in Intersight may appear as disconnected as follows:

![](assets/images/Picture36.png)

Please click on the vSphere Target, edit, select "Datastore Browsing Enabled" and Save your new config. You should see the Target change back to "Connected" state on a Refresh.

![](assets/images/Picture37.png)

## Generate API keys

In this step, generate the API keys that you will upload to TFCB workspaces.

On the **Settings** tab at intersight.com, generate the API key. 

![](assets/images/Picture10.png)

Store the key ID and secret key. You will need this information for the next step:

![](assets/images/Picture11.png)

## Upload Intersight API keys to TFCB workspaces

Return to the TFCB workspace to upload the `api_key` and `secretkey` to the following TFCB workspaces to initialize the Intersight TF Provider:

* `sb_iks_xxx` 
* `sb_k8sprofile_xxx` 
* `sb_iksdelete_xxxx`

Open each workspace and click **Configure variables**. In the **Terraform Variables** section, add the `api_key` and `secretkey` as sensitive variables.

## Generate and upload ssh keys to the TFCB workspace

Generate ssh keys on the Sandbox DevBox. You can get the SSH credentials for your DevBox from your Sandbox:

![](assets/images/Picture121.png)

Use your terminal to connect to the DevBox via ssh.

```bash
ssh developer@10.10.20.50
```

When you have logged in, generate and save the private ssh key in a known location. You need the keys to log into cluster nodes later in this Learning Lab.

```bash
ssh-keygen -t ed25519
```

Open the file where you saved the key with `vim` or `nano` and copy it.

Return to the `sb_iks_xxx` workspace in TFCB. Add the variable `mgmtcfgsshkeys` and mark it as sensitive.

![](assets/images/Picture12.png)


**Next: Execute the TFCB plan to create IKS policies**
