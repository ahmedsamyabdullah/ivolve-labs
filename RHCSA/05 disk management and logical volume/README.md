# Labs RHCSA
# Lab 5: Disk Management and Logical Volume
****
Step 1:
Display current disks before add new disk by command => lsblk
![current disks](./lab5%20imgs/01%20before%20add%20new%20disk.PNG)
****

Step 2:
Display current disks after add new disk by command => lsblk
![current disks](./lab5%20imgs/02%20after%20add%20disk.PNG)
****

Step 3:
Create new partitions by using command =>  sudo fdisk /dev/sdb
![fdisk command](./lab5%20imgs/03%20fdisk%20command.PNG)
****

Step 4:
create partitions (5G,5G,3G,2G)
![create first two partitions](./lab5%20imgs/04%20create%20partitons%20part01.PNG)
![create last two partitions](./lab5%20imgs/05%20create%20partions%20part02.PNG)
****

Step 5:
verify new partitions added
![verify new partitions](./lab5%20imgs/06%20verify%20new%20partitions.PNG)
****

Step 6:
Partition 1: Format as a File System ... Format /dev/sdb1 as ext4 => mkfs.ext4 /dev/sdb1
![format partition 1](./lab5%20imgs/07%20format%20partition%201.PNG)

Create a mount point and mount it:
command=> sudo mkdir /mnt/disk1
command=> sudo mount /dev/sdb1 /mnt/disk1
![mount partition 1](./lab5%20imgs/08%20mount%20partition%201.PNG)

Partition 2: Configure as Swap...Set up /dev/sdb4 as swap:
command=> sudo mkswap /dev/sdb4
command=> sudo swapon /dev/sdb4
command=> swapon --show
![make swap](./lab5%20imgs/09%20make%20swap.PNG)

Partition 3: Configure as a Volume Group with Logical Volume
Create a Volume Group (VG) named vg_data using /dev/sdb2
command=> sudo vgcreate vg_data /dev/sdb2
![vgcreate](./lab5%20imgs/010%20vgcreate.PNG)

Create a Logical Volume (LV) named lv_data with the entire VG
command=> sudo lvcreate -l 100%FREE -n lv_data vg_data
![lvcreate](./lab5%20imgs/011%20lvcreate.PNG)

Format the LV as ext4
command => sudo mkfs.ext4 /dev/vg_data/lv_data
![format lv_data](./lab5%20imgs/012%20format%20lv.PNG)

Mount the LV
command ==> sudo mkdir /mnt/lv_data && sudo mount /dev/vg_data/lv_data /mnt/lv_data
![mount lv_data](./lab5%20imgs/013%20format%20lv.PNG)

Partition 4: Extend the Logical Volume
Add /dev/sdb3 to the VG:
command => sudo vgextend vg_data /dev/sdb3
![extend vg](./lab5%20imgs/014%20extend%20vg.PNG)

Extend the LV to include the new space
command=> sudo lvextend -l +100%FREE /dev/vg_data/lv_data
![lvextend](./lab5%20imgs/015%20lvextend.PNG)

Resize the file system to use the extended space
command=> sudo resize2fs /dev/vg_data/lv_data
![resize file system](./lab5%20imgs/016%20resize.PNG)

Verify new space
command => df -h
![verify new space](./lab5%20imgs/017%20verify%20new%20space.PNG)

Verify LVM
![verify LVM](./lab5%20imgs/018%20verify%20lvm.PNG)


