VMware VCP6-DCV - 2.0 vSphere Security
============================================================

Title: Hardening vSphere
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-2-3-1-hardening_vsphere_pt1

Harden ESXi Hosts
------------------------------------------------------------

* ESXi Services
	+ Disable unused services
	+ Most are disabled by default
	+ Configuration
		1. `Hosts and Clusters -> Host -> Manage -> Security Profile`

* ESXi Firewall
	+ Enabled by default
	+ Most services are allowed through
	+ Consider restricting clients allowed to connect
	+ Configuration
		1. `Hosts and Clusters -> Host -> Manage -> Security Profile`

* Host Profiles
	+ Can be used to ensure consistent settings between hosts
	+ Created/Applied from within vCenter
	+ Creating a Profile
		1. `Hosts and Clusters -> Host`
		2. `Right-click -> Host Profile -> Extract Host Profile`
	+ Assigning a Profile
		1. `Hosts and Clusters -> Host`
		2. `Right-click -> Host Profile -> Manage Profile`
			- Select a profile
		3. `Right-click -> Host Profile -> Apply Profile`
	+ Editing Profiles
		1. `Management -> Host Profiles`

* Lockdown Mode
	+ Configuration
		1. `Hosts and Clusters -> Host -> Manage -> Security Profile`

* Network Security
	+ `Hosts and Clusters -> Host -> Manage -> Virtual switches`
	+ Click `Edit` for the appropriate switch
	+ Select `Security`

* Host Web Interfaces
	+ Can be disabled if vCenter is being used
	+ Host Welcome and Datastore Browser
		- `vim-cmd proxysvc/remove_service "/" "httpsWithRedirect"`
	+ Managed Object Browser (MOB)
		- `vim-cmd proxysvc/remove_service "/mob" "httpsWithRedirect"`
	+ To put them back:
		- `vim-cmd proxysvc/add_tcp_service "/" httpsWithRedirect localhost 8309`
		- `vim-cmd proxysvc/add_np_service "/mob" httpsWithRedirect /var/run/vmware/proxy-mob`
