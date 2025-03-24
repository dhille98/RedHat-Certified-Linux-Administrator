# Booting Procedure and Kernel Parameters 

* BIOS
* MBR (Basic Input / Output System)
* GRUB (Master Boot Recorder)
* Kernel
* init
* Runlevel


* when ever turn on Liunx server sevaral stages run 
        * frist one was starting on BIOS
        * excuting on MBR
        * it will excuting on GRUB
        * GRUB will excuting on Kernal
        * Kernal will excuting on Init
        * Init will excuting on Runlevel
        * all service up and running, go and excuting commands 
* kernal mail role controling the security and manging the roles

* **BOIS**
      * BOIS stand for basic Input / Output System 
      * BOIS stand for system integration check (cheking for Hardware)
      * Bois searching and loading , excuting on our Bootloader that is MBR
* **MBR**
      * it is located in the frist sector of bootable disk 
      * `MBR` less then `512 bytes`, this will divided into three parts 
          * primary Boot Loader (446b), it is having in the primary boot loader information 
          * partition table informations(64 bytes)
          * MBR validation check allocated into into (2bytes)
      * MBR contains information about GRUB 
      * this load excuting on GRUB
* **GRUB**
    * Grub is store informatins about the kernal
    * GRUb in file `boot/grub/grub.conf` or `/etc/grub.conf` in this file kernal image information store 
    * 
    * Grub dispaly the flash screen wait for few sec, you don't enter any thing by take a default kernal 
    * GRUB has Knowledge filesystem 
  
* **Kernal**
    * `Kernal` is interpreter intract with *hardware and shell* 
    * Q. which is last programe has to be excuted in the operating system in booting process
    * last programe is `initrd` in the file `/etc/rc` in the init programing `PID` of `1`
    * `initrd` means intilazation of ram disk

* **INIT**
    * run levels are backround process Deamon responcebul run your servicess 



* runlevels showed for `/etc/inittab`
    * run levels are 
        * 0  --> halt (it is not going to bootup `suspended`)
        * 1  --> single user mode
        * 3  --> Full multiuser, without NFS
        * 4  --> unused
        * 5  --> x11
        * 6  --> reboot (set the by default our system will continous reboting)
* `chkconfig --list` do able to see which are process in the what runlevels
* if you forgate the root user passwords use that run level 1 
* runlevel 2 is used for multiusermode without NFS used for
* NFS is shararing data from one linux meachine to another Linux using 
* runlevel 3 is only cli mode 
* runlevel 5 is GUI and CLi mode 
* change the runlevels on linux server using on ` vi /etc/inittab`
* 

---

## **1. Traditional SysV Init Runlevels**
In older Linux systems using **SysVinit**, runlevels are defined as follows:

| **Runlevel** | **Description** |
|-------------|---------------|
| **0** | Halt (Shutdown) |
| **1** | Single-user mode (Rescue mode) |
| **2** | Multi-user mode without networking |
| **3** | Multi-user mode with networking (CLI mode) |
| **4** | Unused (Can be customized by the user) |
| **5** | Multi-user mode with GUI (Graphical Mode) |
| **6** | Reboot |

- **Check current runlevel**:  
  ```bash
  runlevel
  ```
- **Change runlevel**:  
  ```bash
  init <runlevel>
  ```
  Example:  
  ```bash
  init 3   # Switch to CLI mode
  init 5   # Switch to GUI mode
  init 0   # Shutdown
  ```



