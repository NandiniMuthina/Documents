# VIOS_cmd's

 Login : ssh padmin@<vios_ip>
 username/password : padmin/padmin

`These are several commands to check for free disk space before creating vios partitions.`

## lsdev
 - lists all the devices
 - (ent0,ent1,ent2,ent4 are ethernet interfaces)

## lsdev -type adapter
 - lists all adapters including ent, fc and virtual

## entstat -d <ent>
 - gives more info about that particular ent.

## fcstat <fcs>
 - gives more info about fc adapter

> hdisk-->harddisk 

## lsdev | grep hdisk
 - it will show hdisk name and adapter 

## ifconfig -a 
 - it will show ip configurations

## lspv
 - list physical volumes

> PVID-->physical volume id
> VG-->volume group

## lspv <hdisk>
 - gives the details regarding hdisk,free page partitons and used page partitions.

## lsmap -all
 - gives vtd(Virtual Target Device) info
 - Cient(lpar) and server(vios) if mapped, those details will appear here.

## mklv -lv <logicalvolume_name> rootvg <desiredmemory>
 - make logical volume (in place of logicalvolume_name -> user can give volume name) by using the group name rootvg and allocating desired amount(ex:400G) of memory to it. 

## lsmap -all -net
 - gives sea info

## mkvdev -vdev bastion_lpar -vadapter vhost0
 - make virtual device(-vdev) named bastion_lpar and virtual adapter for the virtual host0.

**after entering the above command, we can get the list of details for (lsmap -all)**

## rmvdev -vdev mn1_lpar
 - deletion (remove virtual device  mentioning mn1_lpar(masternode1_lpar) as example)

## rmdev -dl <ent>
 - removes the mentioned ent adapter.
