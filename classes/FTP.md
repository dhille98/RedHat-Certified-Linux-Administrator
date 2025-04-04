# File Transfer Protocal (FTP)

* what is FTP ?
* Types of FTP
* Active and passive 
* What is diffrent b/w Active and Passive FTP
* FTP SERVER CONFIGURATION 
* FTP CLIENT CONFIGURATION 
* FTP Commands 

* client to server to commnicate with easy 
* server to server commnications 

* **ACTIVE FTP**
* FTP ports are 20, 21
* 20 is establishing the connections (client and server) that is called as command controll
* 21 is establish the `data connections` it is initiates with server
* that is called the  Active FTP

* **Passive FTP**
* both connection do on client (command control and data connections)

* **FTP Server**
* Profile of FTP Server
* Use: ftp is used for uploadling and downloading the files
* Disadvantage: Directory cannot be uploaded or downloaded.
* Package: vsftpd
* Daemon: vsftpd(very secure ftp daemon)
* Script: /etc/intid/vsftpd
* Port No: 20 & 21 
* configuration files : /etc/vsftpd/vsftpd.conf
                      : /etc/vsftpd/user_list
                      : /etc/vsftpd/ftpuser
                      : /etc/pam.d/vsftpd
* Profile of FTP Server 
* Documents Root : /var/ftp
* Home directory : /var/ftp 

* Deamon's are nothing but run the backround process wich run the diffrent runlevels

---
configure the ftp server 
        * frist add the remote server on file on `/etc/host/` 
        * check the filewalls status `service iptable status` any firewalls are on lets stoped that one 
        * start the `service iptable start` and check the status `service iptables status` 
        * now the iptables runlevel check `chkconfig --list iptables` 
        * change the run levels using command like `chkconfig --level 12345 iptables on`
1. Install the package
2. Create some files in /var/ftp/pub directory
3. Restart the service
4. Make the service enable even after reboot of the system
5. Connect from client and access the files and download it