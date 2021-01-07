VMware VCP6-DCV - 3.0 vSphere Networking
============================================================

Title: Configuring Distributed vSwitches
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-3-2-1-configuring_distributed_vswitches_pt1

Configuring Distributed vSwitches (Part 1)
------------------------------------------------------------

#### Distributed vSwitches

+ Allows a standard vSwitch to span multiple ESXi hosts
+ Requirements:
	- vCenter Server
	- vSphere Enterprise Plus
+ Advantages over a standard vSwitch
	- Can traffic shape inbound and outbound traffic (vSwitches can only shape outbound)
	- Single configuration across multiple servers
	- Improved load balancing when using NIC teaming (balancing done via LACP)
	- Enhanced monitoring and reporting
	- IEEE 802.1p Tagging for QoS
	- Port Mirroring (SPAN - Switch Port ANalyzer)
+ dvSwitches are updated with each release of ESXi
	- e.g. Distributed Switch 5.5.0
+ Can be replaced with a Cisco Nexus 1000V Virtual Switch
+ Create a dvSwitch
	1. `vSphere Web Client -> vCenter -> Distributed Switches -> Create a new distributed switch`
	2. Create the dvSwitch
	3. Create a dvPortGroup and assign physical NICs
	4. Assign policies to the dvPortGroup if desired
+ Add hosts to the dvSwitch Port Groups
	1. `Home -> Networking -> dvSwitch -> Manage -> Settings -> Topology`
	2. Click `Add hosts` button (Two servers with a wrench)
	3. During the wizard, you can opt to move the VMs too
+ Add VMs to the dvSwitch Port Groups (If not done above)
	1. `vSphere Web Client -> vCenter -> VMs and Templates -> VM -> Manage -> Edit -> Network Adapter`
+ Upgrading a dvSwitch
	1. Upgrade vCenter and all affected ESXi hosts first
	2. `vSphere Web Client -> vCenter -> Distributed Switches`
	3. Right-click the dvSwitch and choose upgrade

