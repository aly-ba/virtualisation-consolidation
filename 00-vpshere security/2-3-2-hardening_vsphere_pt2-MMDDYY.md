VMware VCP6-DCV - 2.0 vSphere Security
============================================================

Title: Hardening vSphere (Part 2)
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-2-3-2-hardening_vsphere_pt2

Hardening vCenter Servers
------------------------------------------------------------

* VMware Certificate Authority (VMCA)
	+ Manages certificates for vCenter
	+ Part of the Platform Services Controller
* Server Certificate
	+ Self-signed certificate generated during installation
	+ vCenter can act as a CA
	+ Not trusted by anyone
		- Clients would need to add the CA cert to their 
		  trusted root authorities
	+ Can be used, but a trusted cert would be better
* Management
	+ GUI: `Administration -> System Configuration -> Nodes -> Node -> Manage -> Certificate Authority`
	+ CLI: `C:\Program Files\VMware\vCenter Server\vmcad\certificate-manager.bat`

Hardening Virtual Machines
------------------------------------------------------------

+ Control VMware Tools installation
	- VMware Tools provide services for many vSphere functions
	- Access to the tools can be restricted
		1. `Administration -> Roles -> Edit Role`
		2. `All Privileges -> Virtual Machine -> Interaction -> VMware Tools Install`

+ Control VM data access
	- The ability to move files between the VM and a client
	- Can be restricted
		1. `Administration -> Roles -> Edit Role`
		2. `All Privileges -> Virtual Machine -> Interaction -> Drag and drop`

+ Virtual machine network security policies
	- Can limit certain types of traffic from reaching a VM
	- Not a replacement for a firewall
	- Defined on the vSwitch
	- Can protect the guest from DoS attacks
		+ Does not protect your physical switch
		+ Does not protect your ESXi host
	- Configuring
		1. `Home -> Hosts and Clusters -> Host`
		2. `Manage -> Networking -> Virtual Switches -> Edit`
		3. Configure `Security`
			- Promiscuous Mode
			- MAC Address Changes
			- Forged Transmits
		4. Configure `Traffic Shaping`
			- Average Bandwidth
			- Peak Bandwidth
			- Burst Size

+ Control VM-VM communications
	- Consider using separate virtual switches
	- Consider using separate physical network adapters

+ Control VM device connections
	- Typically can be controlled from within the guest OS
	- Can be controlled for vCenter
		1. `Administration -> Roles -> Edit Role`
		2. `All Privileges -> Virtual Machine -> Interaction -> Console Interaction`


