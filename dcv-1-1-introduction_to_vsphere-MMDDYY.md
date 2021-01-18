VMware VCP6-DCV - 1.0 Installing vSphere 6
============================================================

Title: Introduction to vSphere
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-1-1-introduction_to_vsphere

1.1 Introduction
------------------------------------------------------------

* What is VMware vSphere
	+ Software suite built around virtualization
	+ Primary Products
		- VMware vSphere Hypervisor
			+ aka ESXi
				- Elastic Sky X Integrated
			+ aka VMvisor
			+ Type 1 Hypervisor
			+ Considered the "core" product
		- vCenter Management Server
			+ Centralized management of hypervisors
		- Platform Services Controller
			+ Provides SSO, licensing and certificate management
	+ [vSphere Editions](https://www.vmware.com/products/vsphere/compare)
		- vSphere Essentials
			+ Hypervisor
				- Hypervisor is named "VMWare vSphere Hypervisor" 
				- Sometimes called VMVisor
				- The old name is ESX and is used frequently on the exam and in real life
				- ESX stands for "Elastic Sky X" although no one uses that
				- ESXi stands for "ESX Integrated"
		- vSphere Essentials Plus
			+ vMotion
			+ High Availability
			+ Data Protection & Replication
			+ vShield Endpoint (Anti-virus & Anti-Spyware)			
		- vSphere Standard
			+ Fault Tolerance
			+ Storage Motion
		- vSphere Enterprise
			+ Distributed Resource Scheduler and Distributed Power Management
			+ Storage APIs for Array Integration, Multipathing
			+ Big Data Extensions (Hadoop cluster support)
				- Hadoop clusters separate systems into compute and data nodes
				- Compute nodes can be added/removed as needed to provide scale
			+ Reliable Memory
				- Detects errors and removes from the active pool
				- Enough corrected errors at an address will cause it to be blacklisted
				- Acts upon corrected errors instead of uncorrected errors
		- vSphere Enterprise Plus
			+ Distributed Switch
			+ Storage DRS and Profile-Driven Storage
			+ I/O Controls (Network and Storage) and SR-IOV
			+ Host Profiles and Auto Deploy
			+ Flash Read Cache
			+ Application High Availability (App HA)
	+ "With Operations Management" 
		- Adds vCenter Server
			+ Health Monitoring and Performance Analytics
			+ Capacity Management and Optimization
			+ Operations Dashboard and Root Cause Analysis
		- vCenter Server Essentials
			+ Basic management for a single host
		- vCenter Server Foundation
			+ Basic management for up to three hosts
		- vCenter Server Standard
			+ Full feature set including performance management and provisioning
	+ Licensing
		- Unlimited memory and cores as of v7
		- Licensed per physical CPU
		- "Acceleration Kits" or starter packs normally include 6CPUs and 1 vCenter Server. 
	+ [Pricing](http://www.vmware.com/products/vsphere/pricing)
* Other VMWare products that build on vSphere
	+ VMWare Horizon (with View)
		- VDI Infrastructure built on top of vSphere
	+ VMWare SRM
		- Site Recovery Manager
		- Automated disaster recover solution
