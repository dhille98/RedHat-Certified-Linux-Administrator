# User Mnagement in Linux 

### Local User Management 

`whoami/who am i`    ---> this commands help you current user name
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
* 