UNIX 
-----

* Originated as  research project at AT & T Bell Labs in 1969 by Ken Thompson and Dennis Ritchie 

* 1991 linus Torvalds created a Uinx-like system to run on intel processor


UNIX flavours 
------------
* hp UX
* IBM AIX
* Mac OS
* Solaris oracle 

Linux flavours 
--------------
* Red hat 
* CentOS
* Ubuntu 
* fedora 
* suse
* kali 

Feature of Linux 
----------------
* High Security 
* Hight Stability 
* Ease of Maintenance 
* Hardware Independent 
* Freely Available 
* Distributed OS
* Supports ALL File System 
* Multiuser, Multitasking OS 
* Open Source
* Ease of Use 
* Customization 
* Education 
* Support 
* Better Process Handling 


### Linux Kernal 

* Linux `kernal` is bridge between user and hardware. 
* OS is bultin into three pieces 
      * KERNAL --> CORE 
      * SHELL --> working on commands 
      * HARDWARE 

* **Shell** 

* Provides a powerful interface to the UNIX Operating system so you can manipulate data and execute sevaral applications under certain conditions 
* Also known as the *command-line* interface 

### Linux Booting Procers

**BIOS**
* Basic Input Output system 
* BOIS is a combination of both hardware as well as software 
* BOIS provides us options to choose a boot device 
* Then it gives the control to MBR (MBR)

**MBR**
* master Boot Record
* Provides us a boot selection menu to choose a particular OS with which we want to boot our machine.
* it contains the inforamtion about the boot loader.
* then it handovers the control to the boot loader.

**GRUB**
* Grand Unified Bootloader 
* GRUB is a file located in the address `/boot/grub/grub.conf`
* the older version of Linux Bootloader is LILO (Linux Loader).
* the latest version of LINUX Bootloader is GRUB2.
* IT contains information about Linux Kernal & initial (basic) Ram Disk.
* it also contains inforamtion about the particular partition in which the root file system is loaded 
* then it gives control to the kernal.

**KERNEL**

* The name of th Linux kernal is `VM-Linuz`
* it intreacts between machine hardware and shell 
* After getting control from the GRUB, KERNAL loads its splash image frist with the help of initramfs, file which are accessed even with out mounting the HDD.
* then it transfers the control to the INIT.


**INIT**
* INIT is the frist process of Linux OS.
* INIT is also know as the partent of all processes.
* the process ID of INIT process is 1.
* After loading itself then it loads the whole OS 
* there are several run levels in Linux which works on INIT values.


**Linux Run Levels**
- Run Level 0 = INIT 0 --> Shut Down
- Run Level 1 = INIT 1 --> Single User Mode Without GUI & NFS
- Run Level 2 = INIT 2 --> Multi User Mode without Network FS 
- Run level 3 = INIT 3 --> Multi User Mode with NFS 
- Run level 4 = INIT 4 --> Research Purpose
- Run level 5 = INIT 5 --> X11 (Linux Graphics)
- Run Level 6 = INIT 6 --> Reboot 

* `INIT` is replaced with `Systemd ` now as RHEL8

**Linux file system**

/bin --> *essential user command binaries*
/etc --> *configuration files for the system*
/sbin --> *essential system binaries*
/usr --> *read-only user application support data & binaries*
/var --> *variable data files* 
/dev --> *devices files* 
/home --> *user home directories*
/lib --> *libraries & kernel modules*
/mnt --> *mount files for temporay*
/opt --> *optinal software application*
/proc --> *process & kenal inforamtions*
/root --> *home dir for root directory*