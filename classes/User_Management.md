# User Mnagement in Linux 

### Local User Management 

`whoami/who am i`    ---> this commands help you current user name / which user use the system
* `who`     ---> this command help you ha been loged into a your systems and detail informations.
* `w`       ---> this command will show the when the user login and how much cpu usages 
* `id`      ---> this command will show user id. do want to know the spefic user id `id -u <username>`.
* `su`      ---> use the switch one user to anther user
* `visudo`   ---> this will show the sudors file in linux.
    * in this file user only excute only spefic commands or all commands 
* user informations stored on  `/etc/passwd`


* service accounts /system users--> 0-999 this are system users 
* after enter command `useradd dhille` by default set this user join which bash, home directory. every thig store on `/etc/default/useradd / useradd -D`
* see the diffrent shells in linux use the commands `chsh -l`
  

# Password Management in Linux 

* `/etc/shadow` is keeping the passwords on users 
* `/etc/login.defs` in this file informations about the password length, max days ...etc 
* `chage` command used for chage the age password 
* `chage -l <user> ` deatils of the user password 
* disiable the password use the commands `vi /etc/shadow` and use the syable `!` on second colume.
* lock the user account by using command is `usermod -L <user>`. or using the `vi /etc/passwd` and change the shell `/bin/nologin`
* unlock the user account command is `usermod -U <>`


# User & Group administration

## part-1 : USER ADMINISTARTIONS 

* check ip of linux `ifconfig`
* same system login with one or more users
* user should be identify *username* and *userid* 
* **Why we need on user administartions**
      * user and group are used to conrol access to files snd resources
      * Users login to the system by supplying their username and password 
      * Every file on the system is owned by a user and associated with a group 
      * Every Process has an owner and group affiliation, and can only acess the resources its owner or group can acess.
      * Every user of the system is assigned a unique user ID number ( the UID)
      * user name and UID are stored in */etc/passwd*
      * user's passwords is stored in */etc/shadow* in encrypted form.
      * Users are assigned a home directory and a program that is run when they login (useually a shell)

* /etc/shadow file store the user realted passwords, that all about the security, priveliages, all user cannot access the files, only root user can acesses on file 


### types of users on Linux system 

* super user          Root    0       0   /root   /bin/bash
* System User         ftp,ssh,apache,nobody     1-499   1-499   /var/ftp    /sbin/nologin
* Normal user         name of the users     0   0   1000-60000  1000-60000 /home/users     /bin/bash

### User & Group Adminnistration

* important files on Linux Adminstrator 
      * /etc/passwd
      * /etc/shadow
* in */etc/passwd* file inforamtions in 7 fields 
        - username
        - x --> link on passwd file of /etc/shadow
        - UID
        - GID
        - comment (brief information about the user)
        - home directory of users
        - shell 
* in */etc/shadow* file inforamtions in 9 fields 
      -   user name
      -   passwd 
      -   days since that passwd changed
      -   days after which password must be chaged
      -   days before password is to expire that is warned 
      -   days after the password is expires that the user is diabled.
      -   A reserved field 
  
## Real-rime Production Enviroment Hads on

**1.Creating user's by below attributes**

          * *syntax:* useradd or adduser <username>
              * -u userID of the new account
              * -G list of supplementary groups of the new account 
              * -g name or ID of the primary group of the new account 
              * -d home directory of the new account 
              * -c --comment COMMENT
              * -s --shell SHELL login shell of the new account 
**2.Modifying the user's attribute**

            * Syntax: usermod <options> <username>
              * -l to chage the login name
              * -L lock the account
              * -U to unlock the account 
**3.Changing the password parameters**

            * Syntax: chage <username> or <options><value><username>
              * -m for Min password age
              * -M for Max password age 
              * -d for last time the password is changing
              * -l Passwor inactive [-1 means inactive]
              * -W password expiration warnings
              * -E A/C expiration data
  

* **play with Linux Usermagement commands**
  * when ever creating user on Linux by take that by default `Homedir` and default `Shell` in this values comming from file called `/etc/login.defs`
  * `/etc/login.defs` in this file stored form information on `UID/GID` 
  * creating with user on Linux pass that dispaly name chage the home dir
        * `useradd -c "reating demotest2" -d /var/demotest2`
  * changing the user home directory and shell using command 
        * `usermod -d /home/demotest1 -s /sbin/nologin demptest1`
  * creating group `groupadd -g 1030 demoetest4`
  * creating user on particalar group use command
        * `adduser -u 1030 -g 1030 -c "demotest4" -d /var/demotest4 demotest-4`
  * set the password on user `passwd <username>`
        * `/etc/passwd` in this file store the encrypted passwd on user
  * changing the user display on or name using command 
        * `usermod -l linux01 demotest1`
  * lock this account use command 
        * `usermod -L <username>`


* Changing the password parameters on two ways 
        * using command call `chage`
        * modifiy the file on `/etc/logindefs`
        * chage 
* set the password never expreied
    * using commands `chage <username>`, in the password age section `enter -1`
    * check that use `chage -l`
* deleteing user on Linux server on `userdel  <username>`


## Some Important Points realted to Group Administration
* User are assigned to group with unique group number (the GID)
* group name and GID are stored in `/etc/group`
* Each user is given their own private group
* They can also be added to thier groups to gain additional access 
* all users in a group can share files that belongs to the group

* `/etc/gshadow` store on group passwords 

* creating group using commad `groupadd <>`
* set the password for the group on `gpasswd <group_name>`
* modifying the properties of the group
      * `groupmod <opt><arg><group_name>`
          * -g  to change the group
          * -o to override the previous assigned id
          * -n to change the group name
* user add on spefic group use the commands 
        * `usermod -G <group_name> <user_name>`
* removing the user form a group 
      * `gpasswd -d <user_name> <group_name>`

### Adding and Removing Mebers to group 
* *Syntax* usermod -G <group_name><username>
        * -G adding a secondary group to the user 
        * -M for adding multiple user to a group
        * -a for adding a single user to a group
        * -d removing a user from a group

