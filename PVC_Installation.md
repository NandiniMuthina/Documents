# PVC 
  - Advanced Virtualization and Cloud management Offering.
  - Simplified Virtualization management and cloud deployments for IBM machines.
  - With PowerVC, we can manage HMC, Power Servers, Novalink , storage, Network...etc
## Steps for PVC Installation (X86/Power)
   - commands for registering Red Hat Network (RHN), enabling repositories, and installing PowerVC's operation manager. 
   - Here is a brief explanation of each command:
   ```
     wget --user <ftp3-id> --ask-password -O ibm-rhsm.sh ftp://ftp3.linux.ibm.com/redhat/ibm-rhsm.sh
   ```
   - This command downloads a script called ibm-rhsm.sh from an FTP server and saves it to the local file system.
   - The --user and --ask-password options are used to provide authentication credentials to the FTP server.
### Note

   > User can get the command based on their requirement by using grep command.
   ```
   subscription-manager repos --list | grep "high"
   ```
   ```
   subscription manager repos --list | grep "ansible"
   ```
   - This command will gives us list of commands among those, we can choose for Power architecture or X86 based on our requirement.
   ```
    subscription-manager repos --enable=rhel-8-for-x86_64-highavailability-rpms
   ```
   - This command enables the Red Hat Enterprise Linux (RHEL) 8 High Availability repository for x86_64 architecture.
   ```
    subscription-manager repos --enable=ansible-2.9-for-rhel-8-x86_64-rpms
   ```
   - This command enables the Ansible 2.9 repository for RHEL 8 x86_64 architecture.
   ```
    yum install python3.9
   ```
   - This command installs Python 3.9 from the default repositories using the yum package manager.
   ```
    alternatives --config python3
   ```
   - This command configures the python3 command to use Python 3.9 instead of the default Python version.
   ```
   update-alternatives --set python3 /usr/bin/python3.9
   ```
   - The above command can be used to update alternatives of python to python3.9
   ```
    sed -i "/pam_wheel.so.*use_uid/d" /etc/pam.d/su: 
   ```
   - This command removes a line from the su PAM configuration file to disable wheel group restriction on the su command.
   ```
    setup_opsmgr.sh
   ```
   - This command runs a setup script for PowerVC's operation manager.
   ```
    powervc-opsmgr inventory -c <cluster_name>
   ```
   - This command generates an inventory of the specified cluster using PowerVC's operation manager.
   ```
    powervc-opsmgr install -c <cluster_name>
   ```
   - This command installs PowerVC's operation manager on the specified cluster. 


