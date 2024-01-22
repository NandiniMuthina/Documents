# Configuring VSCSI

1. Choose the VIOS ( Virtual I/O Server) 
2. Profile ( Choose the rofile from the manage profiles)
3. Select Virtual adapter
4. Select SCSI adapter
5. Assigned Virtual SCSI Adapter & Client Adapter ID should be same
6. Select Client partition (basically the lpar)
7. save then Lpar Config
8. go to manage profiles
9. Create Ethernet and Client SCSI adapter
   - Again enter the same VSCSI adapter ID and sever adapter ID as same numbers and select server partition (basically VIOS)
   #### save
  - post making changes  -> shutdown  -> activate 


## cmd's 
- lsdev | grep adapter - see the VSCSI added in VIOS profile )
- lsdev | grep hdisk   - see the harddisks connected to VIOS
- lspv -size           - size of each of harddisks in gigabytes
- lsmap -all           - where the vhost is mapped to
- lsvg                 - shows the virtual group name
- lspv                 -  
- mkvg -f -vg rootvg hdisk0 
  - Here we can create new vg ( rootvg is the name of vg wanted to create) ( hdisk is on which you wanted to create)
- mklv -lv RHEL9lpar_os rootvg 150G
  - for creating logical volume, RHEL9lpar_os is the name specifying OS, then trying to check out the space.
- mkvdev -vdev RHEL9lpar_os -vadapter vhost0
  - This logical volume we can connect it to virtual host.
  --> then VSCSI available.

