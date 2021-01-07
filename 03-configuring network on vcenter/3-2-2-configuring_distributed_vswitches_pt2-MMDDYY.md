VMware VCP6-DCV - 3.0 vSphere Networking
============================================================

Title: Configuring Distributed vSwitches
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-3-2-2-configuring_distributed_vswitches_pt2

Configuring Distributed vSwitches (Part 2)
------------------------------------------------------------

####  vSwitch and dvSwitch Policies

+ Define advanced features and limits
+ Many policies are available
	- Security - Promiscuous Mode, MAC changes, etc
	- Traffic Shaping
	- VLAN
	- Teaming and Failover (Very common)
	- Resource Allocation
	- Monitoring (NetFlow)
	- Traffic Filtering and Marketing
	- Misc (Port Blocking)
+ Configured on the vSwitch or the Port Group
+ Port Group settings override vSwitch settings
+ Enable Jumbo Frames
	- Edit the properties of the vSwitch itself
	- Jumbo frames use an MTU of 9000 bytes
	- Default MTU is 1500 bytes
+ vSwitch
	1. `Hosts and Clusters -> Host -> Manage -> Networking -> Virtual Switches`
	2. Click `Edit` (Pencil icon)
+ vSwitch Port Group
	1. `Hosts and Clusters -> Host -> Manage -> Networking -> Virtual Switches`
	2. Select desired Port Group
	3. Click `Edit` (Pencil icon)
+ dvSwitch
	1. `Networking -> vCenter -> Datacenter -> dvSwitch -> Port Group`
	2. `Manage -> Settings -> Policies`
	3. Click `Edit` button

