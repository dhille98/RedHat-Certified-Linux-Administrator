# Manage Process 

* processes are threetypes 
    * Interactive Process
        * fg / bg process 
    * System Process or Daemon 
    * Automatic or batch 
          * schduled process 

* every process on child and parent id
* check the process on Linux on `ps -ef` j
* to see the total number of system use the command is `ps -a`
* check the process on user use command like on `ps -u <username>`
* check attached process on terminal tty use command `ps -x`
* check the process on offline and online use command like `ps -aux`
* grep the particalr process check the process `ps -ef | grep <process Name>`
* total 64 singles in Linux system these are `kill -l` 
* kill -1 <PID> this is reload the process
* kill -9 <PID> this is kill the process, agin the start the process
* kill -15 <PID> this is terminating the process 
* kill -20 <PID> this used for stoping the process

* monataring Linux system is used for `top` 


# Set up Priority of Process 

* Conspets :
      *  NICE 
      *  RENICE

* niceness and nice value it's gudie line 
* Linux Niceness value from `-20` to `19`    
* Hight priority from -- `-20` 
* least priority from -- `19`

* set up on nice value from two ways 
      * `nice` command
      * `renice` command
* nice is to schdule paiority of process before starting
* setup on nice value on `nice -n -20 cat > file.txt` and check `ps -elf`
* renice is using for already running for process set the priority value // changing the paiority value 
* setup on renice value `renice 5 <PID> ` check the process `ps -elf`

* `uptime` Command in Linux
      * The `uptime` command in Linux shows how long the system has been running since the last *reboot*. It also displays the **current time, system uptime, number of logged-in users**, and **system load averages**
* load average will show the *last 1 minutes*, *last 3 minutes*, *last 5 minites*
* check the memory on `free -m`






