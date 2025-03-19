# File Permissions 

* **permission are applied on three levels**
      * owner Level
      * Group Level 
      * Others Level
  
* **Access modes are of three types**
      * R       read only
      * W       write / edit /delete / append
      * X       excute / run a command

* Each file or directory has **three types** of permissions:

1. **Read (r)** – View the file content or list directory contents.
2. **Write (w)** – Modify the file or create/delete files in a directory.
3. **Execute (x)** – Run the file as a program or access a directory.
* Permissions are assigned to **three categories** of users:

1. **Owner** – The user who created the file.
2. **Group** – A set of users who share the same permissions.
3. **Others** – All other users on the system.


```csharp
-rwxr--r-- 1 root root 0 Apr 26 19:58 demo.txt


```
Here, `rwxr--r--` represents:

rwx (Owner: Read, Write & Execute)
r-- (Group: Read)
r-- (Others: Read)


