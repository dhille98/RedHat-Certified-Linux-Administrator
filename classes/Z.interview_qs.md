Linux interview qs
-------------------

* **what is port no of SSH**
	- ssh is secure shell using that access that remote server, *port no is 22*
	- `netstat -tunlp`(apt install net-tools) using that is check the port no 
	- 	- p for program name
		- l for state 
		- n for show the numeric value 
		- u show the udp protocols
		- t  show the protocol name 

* **what is main configuration file of SSH** 
	- find <ssh/package_name>
	- check the query the information about on packages use `rpm -qf <path>`
	- what are the package/software installed on check `rpm -ql <arch_of_package>`
	- what is main configuration of the ssh server `/etc/ssh/sshd_config`
	- 

* **How to change the port no.of SSH ?**
	- changing the port no using for on file called as `/etc/ssh/sshd_config` 
	- in this file modified port no 
	- `systemctl reload sshd` run the command 

* **How to Block SSH access for a single user?**
	- `/etc/ssh/sshd_config` in this file below add the line 
	- *DenyUsers harry* -> add the line on below  
	- `systemctl reload sshd` 
	

* **What are the type of files in linux OS?**
	- Regular files (-)
	- directory (d)
	- link files (l)
	- Block Device (b)
	- Character Device (c)
	- Named Pipe (p)
	- Socket (s)
* **What is the difference between file and directory?**
	- files used for store information about date 
	- directory store the information about other files and information 

* **How to check free space on Linux OS?**
	- df -Th
* **how to check size of files and folders on a server?**
	- du -sh * | sort -rn 
	- du -sh * | sort -rn | head 
	- fallocate -l 100M demo.txt
* **How to check open ports on a server?**
	- check the current server using that on `netstat -nltpu`

* **How to check open ports on a remote server without login?**
	- remote server using that one `nmap -A <IP>`

* **What is difference between public and private IP address?**
	-  public ip address using on internet 
	- private networking configuration in intranet with LAN 

* **what is different between hard link vs soft link** 
	- soft link consumed as different inode (*ln -s filename <.>*)
	- hardlink is used for same inode (*ln*)
	- hardlink cannot create across file system 
* **how to check no.of hard links created on for a file** 
	- command called us on "`ll -lrth`" see the second one 
	- `find / -xdev -samefile <file_name>` this command only printed on same inodes 
* **how to find location of hardlink of a file ?**
	-  find / -xdev -samefile <file_name>
* **what is port no.of DNS and DHCP ?**
	- DHCP IS 67,68
	- DNS is 53 supporting on both UDP and TCP by default protocol is UDP 
* what is different between on TCP and 	UDP? 
* **can you explain on fields on /etc/passwd files** 
	- totally 7 fields 
	- username
	- password link // password hash 
	- userid 
	- groupid 
	- display name 
	- user home directory 
	- shell of the user 

* **how to enforce a user to reset password at next login?**
	- using command called --> chage -d 0 <username>
	- check that password age of user using on `chage -l <username>`
* **how to change shell of the user** 
	- usermod -s <shell-name> <username>
	- usermod -d

* **how to change default directory of users going to be create in future?** 
	- modified the file `/etc/default/useradd`
* **what are the common issues you have faced while doing ssh into a server?**
	- username is miss match
	- issue with port number 
	- keys issues 
	- user blocked from server end 
	- tcp wrapper 
	- key permission issue 
