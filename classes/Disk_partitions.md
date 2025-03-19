# Managing Partition & File System

* what is partition ?
    - partitions means to dived single hard drive into that many logical drivers 
* **Disk partition Criteria**
![Preview](./images/Linux-01.png)

    - in the Extended partition dived into multipul logical partitions 
    - `fdisk -l` this command help on disk partitions 
    - in production env must flowon `3P+1E or 1P +1E`
    - any raw disk not more then 3P Primary extended
    - Logical partions created under the Extended Partions 
* **Disk Identification**

    - IDE (Integrated Drive Electronics) `/dev/hda`
    - SCSI (Small Computer System Interface) - `/dev/sda`
    - Virtual Drive - `/dev/vda`
* **What is file system? Types of file system ?**
    - check the filesystem on Linux server `mkf`
* **Types of file System**
    - ext2
        - Ext2 stands for second extended file system
        - Ext2 does not have journaling feature
        - Maximum individual file size can be form 16GB to 2TB
    - ext3 
        - Ext3 stands for third extended file system 
        - The main benefit of ext3 is that it allows journaling
        - Maximum individual file size can be from 16GB to 2TB 
    - ext4 
        - Ext4 stands for fourth extended file system
        - Supports huge individual file size and overall file system size.
        - Maxmum individual file size can be from 16GB to 16TB
    - xfs
        - The XFS file system is an extension of the extent file system
        - The XFS is a high preformance 64-bit jouraling file system
        - XFS supports maximum file system size of 8 exbibytes for the 64-bit file system
- Journaling feature --> it is supporting on backup and filesytem is crashed rollback is supporting on journaling feature 

* **Mounting**

* df -h --> show the mounted file system in partitions 
* cat /etc/fstab --> partitions is mounted on permintly on in files 
cat /etc/mtab ---> this is dynamic file this show the temporary mounted files, when the restart linux server this information will be lost 


### Commands 

* `fdisk -l // parted -l`           --> To view the exting partition 
* fdisk (disk name)                 --> Partition Administration using fdisk
* n                                 --> Creating a new partitions 
* w                                 --> Saving the partition 
* partprobe /dev/sdc                --> Updating the partition table without restaring system 
* mkfs.ext4 /dev/sdc1               --> Formating a partition with ext4 file sytem 
* Mounting                          --> Temporary (/etc/mtab) & Permanent(/etc/fstab)
* unmount /directory                --> Un-mounting a directory from partition
* mount -a                          --> Mount all the file system of /etc/fstab