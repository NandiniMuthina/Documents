# LPAR(Logical Partition)

- An LPAR is a subset of the processor hardware that is defined to support an operating system. An LPAR contains resources (processors, memory, and input/output devices) and operates as an independent system.
- Every LPAR acts as a Standalone server with it's own Operating System,CPU &Memory. Multiple LPARS can be created on 1 Physical Power server and can share the hardware resources in an efficient way.
- Resources and partitioning go hand-in-hand. Resources are a system's processors, memory, and I/O slots. A logical partition uses software and firmware to logically partition the resources on a system. I/O slots can be populated by different adapters, such as Ethernet, SCSI, or other device controllers. A disk (both internal and external) is allocated to a partition by assigning it the I/O slot that contains the disk's adapter.
- Logical partitioning (LPAR) is only limited by the total number of hardware resources in the system. For example, a partition could have any number of installed processors assigned to it, limited only by the total number of installed processors. Similarly, a partition could have any amount of memory, limited only by the total amount of memory installed (minus the memory required for partition management/overhead). I/O adapters are physically installed in one of many I/O drawers in the system. However, with logical partitioning, any I/O adapter in any I/O drawer can be assigned to any partition; however, only one partition with that resource can be active.
- One of the main advantages of the LPAR implementation is that it gives fine-grained allocation control over these individual resources, allowing them to be combined in almost any quantity and combination to create a logical partition.
- LPAR tooks I/O resources inorder to provide advanced virtualization capabilities across other client Lpar's.
- It provides Virtual SCSI target, Virtual Fibre channel, shared ethernet adapter and Power VM active memory sharing capability to client lpar's within the system.

## creation
### Login to putty  
 <!--Eg:(perfp10hmc2.aus.stglabs.ibm.com) -->
_use the hmc provided_
```
1. Use `vtmenu` to list all the systems.
2. Choose the system on which you created and activated the partition. ( All the created partitions can be viewed and further actions like os installation can be done here...)

`SMS menu`
3. To Choose NIC adapters select `Setup Remote IPL` 
```
***To check which Network Port is available ***
   `SMS MENU` 
   choose `Network ports`
   Test all the network ports for availability 
```
ALl the available network ports can be listed here.
```
 _Copy Hardware Address_
`the network adapter with '*' are the available adapters`


**Assigning IP Address**

4. Systems Lab Resource Center [SLRC](https://slrc.stglabs.ibm.com/)


```IP/DNS Management --> request an IP (Multiple IP's can be requested)
Select the site, Lab, Subnet, Domain and Assign a Hostname 
Optional Parts can be skipped 

Can view and Manage the assigned IP's under Manage IP(s)
After usage, IP(s)  can be released from here.```

```
**Choose Build**

5.  STG NIM SYSTEM INSTALLATION [pcajet](https://pcajet.aus.stglabs.ibm.com/)

Manual -> nimitz -> hmc_controlled -> SUBMIT

```
Client Name <-> IP address of partition
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
9. It will give a message at the end like attempting to start VNC and displays IP there, use the IP and connect to VNC Viewer.
   Create Password, if needed another user too.
   choose disk to install OS
   Reboot
```
*-------------------Installation will get started-------------------*

login using credentials
Accept the T/C, License..

