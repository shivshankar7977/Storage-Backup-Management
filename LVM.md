## Steps for LVM
```bash
lsblk
```
```bash
pvcreate /dev/sdb /dev/sdc  
```
```bash
pvdisplay
vgcreate HPCSA /dev/sdb /dev/sdc
lvcreate -n hpcsa-lab --size 1G HPCSA
pvdisplay
lsblk
fdisk
clear
 lsblk
 fdisk /dev/mapper/HPCSA-hpcsa--lab
 lsblk
 clear
 lsblk
 mkfs.ext4 /dev/mapper/HPCSA-hpcsa--lab
 mkdir lab
 clear #mkdir lab
 mount /dev/mapper/HPCSA-hpcsa--lab lab/
 lsblk
 lvextend -L +2G /dev/mapper/HPCSA-hpcsa--lab
 lsblk
 vgdisplay
 lsblk
 resize2fs /dev/mapper/HPCSA-hpcsa--lab
 lsblk
 clear
 lvcreate -L 1GB -s -n hpcsa_lab_snap /dev/mapper/HPCSA-hpcsa--lab 
 lvconvert --merge /dev/mapper/HPCSA-hpcsa_lab_snap
 lsblk
 history
 vgs
 clear
 vgs
 lsblk