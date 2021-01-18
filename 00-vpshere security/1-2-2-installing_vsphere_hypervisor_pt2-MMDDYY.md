VMware VCP6-DCV - 1.0 Installing vSphere 6
============================================================

Title: Installing the vSphere Hypervisor
Subtitle: VMware VCP6-DCV
Filename: vmware-vcp6dcv-1-2-installing_vsphere_hypervisor

1.2 – Installing the VMware vSphere Hypervisor (Part 2)
------------------------------------------------------------

* Post-install considerations
	+ ConfigureDNS
	+ Select a CPU power management policy
	+ Enable/Size/Disable memory compression cache
	+ Configure NTP
		- Configure via vSphere Client
		- Can also be done manually
			1. SSH to host
			2. Issue the following commands: 

Lab Notes
------------------------------------------------------------
65
* Getting connected
	1. Execute installer and "next" on through
	2. Launch VMware vSphere Client
	3. Credentials
		- IP: 192.168.0.156
		- Username: root
		- Password: password
	4. Trust the certificate
* License Key
	1. `Inventory -> Configuration -> Licensed Features -> Edit`
* Fixing DNS
	1. `Inventory -> Configuration -> DNS and Routing -> Properties`
* Fixing NTP
	1. `Inventory -> Configuration -> Time Configuration -> Properties`
* Enabling SSH
	1. `Inventory -> Configuration -> Security Profile -> Properties`
	2. Select `SSH`
	3. Select `Options`
	4. Select `Start and Stop with Host` and click `Start`