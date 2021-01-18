VMware VCP6-DCV - 2.0 vSphere Security
============================================================

Title: Role-Based Access Control
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-2-1-role_based_access_control

2.1 Role-Based Access Control
------------------------------------------------------------

* Roles
	+ `vSphere Web Client -> Administration -> Access Control -> Roles`
	+ Clone an existing role to avoid inadvertent permissions
* Add/Modify/Remove permissions
	+ Permissions can be assigned to most objects
	+ Option to propagate to child objects is available at the bottom of the screen
	+ Permissions are determined by combining the user/group/object permissions
	+ `Right-Click Object -> Add Permission`
* Apply permissions to ESXi Hosts using Host Profiles
	+ Create
		- Created from an existing host configuration
		- `vSphere Web Client -> Policies and Profiles -> Host Profiles`
	+ Apply
		- `Right-Click Host -> Host Profiles -> Attach Host Profile`
		- Use `Remediate` to refresh
* Propagation of Permissions
	+ Permissions "trickle down" to related objects
	+ Use the "View Children" option when applying permissions
	+ Always double check newly applied permissions

Lab Steps
------------------------------------------------------------

#### Setup

1. Power on any hosts not automatically powered on
2. Connect to PLABVC01
3. Launch VMware vSphere Web Client
	- IP Address/Name: PLABVC01
	- User name: administrator@vsphere.local
	- Password: Passw0rd!

#### Roles in vCenter

1. `Home -> Administration -> Roles`
2. Highlight default roles and templates
3. Highlight cloning/editing roles

#### Users in vCenter

1. `Home -> Administration -> Users and Groups -> Users`
2. Highlight view, sort and export

#### Groups in vCenter

1. `Home -> Administration -> Users and Groups -> Groups`
2. Select the new group and click the `Add Members` button

#### Configuring the Service Policy

1. `Home -> Administration -> Single Sign-On -> Configuration`

#### Assigning Permissions Globally

1. `Home -> Administration -> Global Permissions -> Manage`
2. Add desired user/group
3. Select role
4. Highlight `Propogate to children` checkbox

#### Assigning Permissions Individually

1. `Home -> Inventory -> Hosts and Clusters`
2. Select desired object
3. `Manage -> Permissions`
4. Add desired user/group
5. Select role
6. Highlight `Propogate to children` checkbox
