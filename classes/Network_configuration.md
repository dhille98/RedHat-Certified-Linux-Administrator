# Network Configuration & Troubleshooting 

* **Basic Requriment**
      - Networking
      - NIC   ---> network interface card 
                - this will connect with computer hardware on network
                - every nic is uniq mac address
                - same vm can create how many nic cards 
                - mac address is uniq on machine
      - Media
                - it is RJ45 cable cat6 cabels
                - it connect with another nic
      - Topology
                - it is schama 
                - 
      - Protocol
                - OSI
                - tcp ip
      - IP Address
      - Gateway

* tcp used for connection orinteded
* udp is used for connection less 

* every network file will be store as `/etc/sysconfig/network-scripts`
* ethernet card store inforamation on `cat ifcfg-eth0`
* change the hostname `/etc/sysconfig/network`


* restart network services used for `/etc/init.d/network restart` or `service network stop/restart`
* `/etc/hosts` this reslove the `DNS` on locally 
* add the any hosts on Linux server using that file `/etc/hosts`
* `/etc/reslov.conf`which keep the address of DNS server client will be accessing reslove the IP to HOST or HOST to IP
* 
** check the Dns is resloving or not
      - `host <IP>`
      - `nslookup <IP>`
      - dig <hostname>
      - ping <ip>
      - 