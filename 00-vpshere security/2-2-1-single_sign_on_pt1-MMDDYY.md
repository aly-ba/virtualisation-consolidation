VMware VCP6-DCV - 2.0 vSphere Security
============================================================

Title: Single Sign-On
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-2-2-1-single_sign_on_pt1

2.2 Single Sign-On (Part 1)
------------------------------------------------------------

* Single Sign-on
	+ Provided by the Platform Services Controller
		- Embedded or external
		- Also provides certificate services
	+ VMware Certificate Authority (VMCA)
		- Part of the PSC
		- Responsible for issuing and managing certificates
		- `Administration -> System Configuration -> Nodes -> Object -> Manage -> Certificate Authority`
	+ Allows re-using accounts from an existing directory
	+ Default is to use a new directory
		- Internal to vCenter
		- Able to be shared between vCenter and ESX systems
	+ Can be configured to support other systems
		- Microsoft Active Directory
		- Microsoft Windows Local Accounts
		- Open LDAP
	+ Can be multi-site
		- When installing vCenter, you choose to join an
		  existing SSO domain


#### Configure Single Sign-on for AD Authentication

1. `Home -> Administration -> Configuration -> Single Sign-On`
2. Select `Identity Sources` tab
3. Click `Add Identity Source`
4. Configure appropriately
	- Type: Active Directory (Integrated Windows Authentication)
	- Domain: practicelabs.com

NOTE: User credentials are not necessary as vCenter box is a
domain member.

Permissions can now be set for AD accounts.

#### Assigning Permissions to an AD Account

Let's say we want to make Domain Admins full administrators
in vCenter.

1. `Administration -> Access Control -> Global Permissions`
2. Select `Manage` tab
3. Click `Add Permission`
4. Click `Add` button
5. Change `Domain` dropdown to show `practicelabs.com`
6. Select *Administrators* group

* Permission Validation
	+ Group membership for user accounts is cached
	+ Can result in unauthorized access until the next refresh
	+ Refreshes always happen when vCenter restarts
	+ Can also be scheduled
	+ Referred to as "permission validation"
	+ Configuration
		1. `vCenter Server -> Manage -> General -> Edit`
		2. Select user directory
		3. Enable/disable validation
		4. Set validity period