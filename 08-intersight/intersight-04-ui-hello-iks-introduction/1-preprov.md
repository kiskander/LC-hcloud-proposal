# Use Intersight UI to provision an IP Pool

As a Cloud Admin, you will allocate IP pools to the various application teams to provision their IKS clusters. You can either create a single pool that can be used for all of the IKS clusters or provision multiple IP Pools and assign each to individual application teams. 

**PLEASE USE THE VALUES SPECIFIED IN THE SNAPSHOTS. THESE ARE THE VALUES THAT APPLY TO THE SANDBOX CONFIGURATION.**

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ippool.png?raw=true)

Provision the following with the Sandbox infrastructure parameters and click **Create**. You can skip the IPv6 tab for now since IPv6 is not supported currently.

```
Subnet Mask 255.255.255.0
Default Gateway 10.10.20.254
Primary DNS 10.10.20.100
Secondary DNS - NA
Start Address - 10.10.20.170
Number - 20
```

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ippool1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/ippool2.png?raw=true)

# Use Intersight UI to provision IKS policies

Next, you provision IKS policies that your DevOps teams will use to provision their IKS cluster. 

**PLEASE USE THE VALUES SPECIFIED IN THE SNAPSHOTS. THESE ARE THE VALUES THAT APPLY TO THE SANDBOX CONFIGURATION.**

The following are the policies that are available for you to configure:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/Picture18.png?raw=true)



__1.__ Configure Kubernetes Version Policy:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/kubever1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/kubever2.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/kubever3.png?raw=true)



__2.__ Configure Network CIDR Policy:

```
POD Network CIDR - 100.65.0.0/16
Service CIDR - 100.64.0.0/24
```

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/netcidr1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/netcidr2.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/netcidr3.png?raw=true)



__3.__ Configure Node OS Policy

```
Timezone - America/New_York
DNS Suffix - demo.intra
DNS Server1 - 10.10.20.100
NTP Server1 - 10.10.20.100
```

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/nodeos1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/nodeos2.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/nodeos3.png?raw=true)



__4.__ Configure Virtual Machine Infra Config:

```
ESXi Cluster - HyperFlex
Datastore - SpringpathDS-10.10.20.121
Interface  - VM Network
Resource Pool - Test_Resource_Pool
vSphere Admin Passphrase - Enter the password that you got in your invitation email
```

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/infra1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/infra2.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images//infra3.png?raw=true)



__5.__ Cofigure Virtual Machine Instance Type

```
CPU - 4
System Disk Size (GiB) - 40
Memory (MiB) - 16384
```

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/inst1.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/inst2.png?raw=true)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/inst3.png?raw=true)



Your policy configuration listing should now looks as follows:

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-04-ui-hello-iks-introduction/assets/images/pol.png?raw=true)


Your DevOps personnel can now provision an IKS cluster that is based on the above policies.
