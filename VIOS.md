# Virtual I/O Server
  - VIOS facilitates the sharing of physical I/O resources between client logical partitions within the server.
  - VIOS provides Virtual SCSI target, Virtual fibre channel, Shared Ethernet Adapter and Power VM active memory sharing capability to Client LPAR's within system.
  - Multiple VIOS can be configured to add some redundancy. So that, the Client LPAR's has the ability to Multiple VIOS. If there is an event of VIOS failure or If going to take it down for planned maintenance, the Client LPAR's still remain active.

## VIOS for multiple functions 
   - Sharing of Physical resources between the LPAR's on system.
   - Creating LPAR's without requiring additional I/O(Physical) resources.
   - Creating more LPAR's than there are..( such as I/O slots or physical devices available with the ability for virtual I/O or physical).
   - Maximizing use of physical resources on the system.
   - Helping to reduce the SAN Infrastructure.

*-------------------Login to HMC(Hardware Management Console)-------------------*
 
<!--Eg : https://perfp10hmc2.aus.stglabs.ibm.com/ --> 

```
1.Select Click on create VIOS
  -> Assign name to vios and Id
  -> allocate processor mode, memory and physical I/O as per the requirement.
 Apply Configuration
     Select Actions 
 Click on Activate
     Go to profile and choose profile ( default/ current configuration) 
 Finish
```
*-------------------VIOS Activated-------------------*

###Login to putty  
 <!--Eg:(perfp10hmc2.aus.stglabs.ibm.com) -->
_use the hmc provided_
```
1. Use `vtmenu` to list all the systems.
2. Choose the system on which you created and activated VIOS. ( All the created VIOS can be viewed and further actions actions can be done here...)

`SMS menu`
3. To Choose NIC adapters select `Setup Remote IPL` 

*** To check which Network Port is available ***
   SMS MENU 
   choose `Network ports`
   Test all the network ports for availability 
  ```

 _Copy Hardware Address_
`the network adapter which '*' are the available adapters`


**Assigning IP Address**

4. Systems Lab Resource Center [SLRC](https://slrc.stglabs.ibm.com/)

```
IP/DNS Management --> request an IP (Multiple IP's can be requested)
Select the site, Lab, Subnet, Domain and Assign a Hostname 
Optional Parts can be skipped 

Can view and Manage the assigned IP's under Manage IP(s)
After usage, IP(s)  can be released from here.

```

**Choose Build**

5.  STG NIM SYSTEM INSTALLATION [pcajet](https://pcajet.aus.stglabs.ibm.com/)

Manual -> nimitz -> hmc_controlled -> SUBMIT

```
Client Name <-> IP address of VIOS
Choose the build as per requirement or latest one
Paste the Hardware Address (get it from SMS Menu at NIC adapters)

SUBMIT.
Info message will be displayed.
```
*-------------------INFO MESSAGE-------------------*
```
6. Revert to SMS Menu ("esc" can be used to revert)

   IPv4 
   - BOOTP -> IP Parameters -> Enter the information obtained from  **INFO MESSAGE** 
7. *PING TEST*

    press esc to revert -> proceed for ping test -> Execute Ping Test -> Ping Success.
8. "esc to revert" 
   Select Boot options -> Select Install/BOOT Device -> Network/(All Devices)
   post this, all the ethernet adapters will be listed down, choose the ethernet adapter ( which is copied from SMS Menu -> NIC adapters)
   choose boot mode ( Normal Mode Boot )
   exit SMS Menu
```
*-------------------Installation will get started-------------------*

login using credentials
Accept the T/C, License..



