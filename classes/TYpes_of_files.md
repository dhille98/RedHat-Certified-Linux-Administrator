# Types of files 

[NotesLink](https://freshertube.com/category/linux/)

* `-`     Normal file
* `d`     Directory file
* `l`     link file (shortcut)
* `c`     character file
* `b`     Blob file (Hard link)


### Symbolic Links (Soft Link and Hard Link)

* **Soft Link:**
      * SHORTCUT FILE
      * if the original file is deleted, link is broken and data is lost
      * inode number of src and link file is different.
      * Can be created across the partition 
      * syntax is --> `ln -s src dest`

* **Hard Link:**
      * BAKUP FILE
      * if original file is deleted then also link will contain the data 
      * inode number of src and link file is same.
      * Cannot be created across the partition.
      *  syntax is --> `ln src dest`

* check the inode value on file using these command `ls -il`
* **INODE**
* `inode` is nothing but it is smalest junk of memory, which going to address file/directory 

* WHY we need a inodes 
    - df -h its will show the details of filesystem 
    - `df -i` command is show the disk inodes if inodes full it will show the error `permissions denied`
    - Q. partions is full (100%) what doing now.
    - inodes full this time crear the inodes and delete/clear the unused files and archive files.



# Filter Commands 

- less      --> see o/p line wise or page wise
- more      --> more is exactly same like less
- head      --> Display the top 10 lines of the file
- tail      --> Display the bottam 10 lines of the file
- sort      --> To sort the output in numaric or alphabetic order
- cut       --> Pick the given expression(in columns)& display the output.
- sed       --> Sed stands for stream editor.
            - strem editor means search the file on words and replace the word to requried to output 
- find      --> Find the file or directory's path (recommended).
- locate    --> Find the file or directory's path(Optional)

```bash
# cut command used 
cut -d: -f1 /etc/passwd  #(d -->means delimiter, -f which filed we want)
# find the user id 
cut -d: -f6 /etc/passwd

# sed command is used 
sed 's/max/john/g' /etc/passwd # s means search word -g means replace word 

```
  
### find and locate command 

* syntax: `find /(under root) -option filename`
* find the file / directory on path location

* **Options**
* -name     --> For searching a file with its name
* -inum     --> For searching a file with particular inode nuber
* -type     --> for searching a particular type of file
* -user     --> For searching a file with respect to its user
* -group    --> For searching a file wich belongs to a particular group 

* find and locate both commands using for searching for files but small diffrent between those 
      * find is more complex pass the options locate does not need
      * locate command is giving on output entier path




