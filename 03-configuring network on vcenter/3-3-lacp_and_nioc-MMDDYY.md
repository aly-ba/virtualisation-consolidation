VMware VCP6-DCV - 3.0 vSphere Networking
============================================================

Title: LACP and NI/OC
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-3-3-lacp_and_nioc

3.3 LACP and NI/OC
------------------------------------------------------------

#### Link Aggregation and Control Protocol (LACP)

+ Verifying LACP Support
	1. `Home -> Networking -> vCenter -> Datacenter`
	2. Select dvSwitch
	3. Select `Summary` tab
	4. Examine the `Features` table
+ Configuring LACP
	1. `Home -> Networking -> vCenter -> Datacenter`
	2. Select dvSwitch
	3. `Manage -> Settings -> LACP`
	4. Click the `+` icon to a *Link Aggregation Group* (LAG)
+ Moving hosts to a Link Aggregation Group (LAG)
	1. Click `Migrating Network Traffic to Link Aggregation Groups` to initiate
	2. Step 1: Add the LAG as a standby to the dvPortGroup
		1. Click `Manage Distributed Port Groups`
		2. Select `Teaming and Failover`
		3. Select the existing port group
		4. Promote the LAG to a standby uplink
	3. Step 2: Move the physical adapters into the LAG
		1. Click `Add and Manage Hosts`
		2. Select `Manage host networking`
		3. Click `+ Attached Hosts` and select desired hosts
		4. Select `Manage physical adapters`
		5. Assign desired ports to the LAG Uplink
	3. Step 3: Make the LAG the only active uplink
		1. Click `Manage Distributed Port Groups`
		2. Select `Teaming and Failover`
		3. Select the existing port group
		4. Promote the LAG and demote the stand alone uplinks

#### Network I/O Control (NIOC) Support
 
+ Network I/O Control (NIOC)
	- Policies that control service bandwidth
		+ Fault Tolerance
		+ Management
		+ NFS
		+ Virtual Machine
		+ Virtual SAN
		+ iSCSI
		+ vMotion
		+ vSphere Data Protection Backup
		+ vSphere Replication
	- Enabled by default
		+ VM traffic is prioritized
		+ Even over vMotion and iSCSI/vSAN
	- Shares
		+ Represent a "share" of the network traffic
		+ Varies based on what is currently being used
		+ Example 1
			- FT: 50
			- NFS: 50
			- VM: 100
			- Totals 200
			- VM gets 50%, FT and NFS get 25% each
		+ Example 2
			- iSCSI: 50
			- VM: 100
			- Totals 150
			- VM gets 66%, iSCSI gets 33%
		+ Values
			- Low (25)
			- Normal (50)
			- High (100) 
			- Custom
	- Reservations
		+ Hold a set amount of bandwidth for a service
	- Resource Pools
		+ A reserved pool of bandwidth that can be divvied up among VMs
		+ Steps
			1. Set a reservation for VM traffic
			2. Create a network resource pool
			3. Assign a port group to the resource pool
				- `dvPortGroup -> Manage -> Settings Properties -> Edit -> Network Resource Pool`

+ Verifying Network I/O Control (NIOC) Support
	1. `Home -> Networking -> vCenter -> Datacenter`
	2. Select dvSwitch
	3. Select `Summary` tab
	4. Examine the `Features` table
+ Enable/Disable NIOC
	1. `Home -> Networking -> vCenter -> Datacenter`
	2. Select dvSwitch
	3. `Manage -> Settings -> Properties -> Edit`
+ Configuring NIOC
	1. `Home -> Networking -> vCenter -> Datacenter`
	2. Select dvSwitch
	3. `Manage -> Resource Allocation`
	4. Right-click desired traffic type and choose `Edit`



