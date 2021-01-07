VMware VCP6-DCV - 3.0 vSphere Networking
============================================================

Title: Configuring vSwitches
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-3-1-configuring_vswitches

Configuring vSwitches
------------------------------------------------------------

* vSphere vSwitches
	+ Two types of networking
		- VM - Connections for Virtual Machines to communicate
		- VMkernel - Connections used for host communications and management
	+ Inter-VM communications can happen entirely in the virtual switch
		- Requires VMs to be combined into a port-group
	+ Configuration
		- `vSphere Web Client -> Hosts -> ESXi Host -> Manage -> Networking -> Virtual Switches`
	+ To Create a vSphere Standard Switch
		- Add Host Networking
			+ Creating a port group without a physical adapter creates an isolated network
			+ Creating a port group with a VLAN attached can carry multiple networks on one physical link
			+ Creating a switch with multiple physical adapters creates a failover/balancing switch
	+ When adding a VMkernel Adapter you can limit its funtionality to:
		- vMotion Traffic
		- Fault Tolerance Logging
		- Management Traffic
		- vCloud Distributed Storage
* Virtual Machine Connections
	+ VMs can be connected to one or more vSwitches
	+ Each adapter is configured independently

#### Lab Steps

1. Examine default vSwitch
	- `Hosts and Clusters -> Host -> Manage -> Networking`
2. Create a VM
	- Create a small Linux VM
	- Show how power state affects link
3. Create a new vSwitch
	- `Hosts and Clusters -> Host -> Manage -> Networking`
	- Select `Add Host Networking` (Blue globe with a +)
4. Create a new VMkernel adapter
	- `Hosts and Clusters -> Host -> Manage -> Networking`
	- Select `Add Host Networking` (Blue globe with a +)
	