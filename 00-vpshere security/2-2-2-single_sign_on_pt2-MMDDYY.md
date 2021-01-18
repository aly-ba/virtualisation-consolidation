VMware VCP6-DCV - 2.0 vSphere Security
============================================================

Title: Single Sign-On
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-2-2-1-single_sign_on_pt1

2.2 Single Sign-On (Part 1)
------------------------------------------------------------

#### SSO Policies

* SSO Policies
	+ Control various aspects of user access
		- Password policy
		- Lockout policy
		- Token policy
* Configuration
	1. `Administration -> Single Sign-On -> Configuration`
	2. Select `Policies` tab

#### Upgrading with SSO

* Always upgrade vCenter/PSC first
* Upgrade ESXi hosts second

#### Joining ESXi hosts to an AD domain

* ESXi hosts can be joined to the AD
	+ Useful for stand-alone deployments
	+ Not necessary with SSO
	+ If you create a group in AD called "ESX Admins" members
	  will automatically be admins in ESX
* Configuration
	1. Verify NTP settings
	2. `Hosts and Clusters -> Datacenter -> Host -> Manage`
	3. `Settings -> System -> Authentication Services`
	4. Click `Join Domain`