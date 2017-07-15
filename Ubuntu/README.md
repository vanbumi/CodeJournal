# Ubuntu 14.04

## Manage User

* [Create new user](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04)

    adduser demo

Root Privileges

    gpasswd -a demo sudo    

* [Delete user](https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-an-ubuntu-14-04-vps)

    $ sudo deluser newuser

* [To list all users](http://askubuntu.com/questions/410244/a-command-to-list-all-users-and-how-to-add-delete-modify-users)
    
        cut -d: -f1 /etc/passwd


## Remove directory

    sudo rm -r -f /path/


## HOW TO ADD A USER TO A GROUP IN UBUNTU 14.04

    https://www.godaddy.com/help/how-to-add-a-user-to-a-group-in-ubuntu-1404-12281
    1. Sign into your server as root.
    2. Create group
        groupadd team
    3. Add user into team 
        sudo add nitza team
    4. Cek user sudah masuk ke group
        groups
    5. List semua group yang ade:
        cat /etc/group
    6. Verify the creation of the group and user
        id dyo 
            >> result: uid=1000(dyo) gid=1000(dyo) groups=1000(dyo),27(sudo),1002(team)
    7. Display the groups to which user belongs with this groups command:
        groups dyo
    8. Removing a user from a group:
        sudo deluser user group    

                
how to list of Groups on ubuntu server
---------------------------------s-----
    cat /etc/group >> ref: http://ubuntuforums.org/showthread.php?t=1583028
    
list all the groups, including ones used only by the system:
------------------------------------------------------------
    groups
    
Switching to the Root User on Your Linux Server:
------------------------------------------------
    sudo su -          << switch to root
    sudo su - dyo      << switch back to user dyo
    
       
ERROR CASE:
-----------
    remote: error: insufficient permission for adding an object to repository database ./objects
    remote: fatal: failed to write object
    error: unpack failed: unpack-objects abnormal exit
        >>> solution: sudo chown -R git:gitgroup path/to/repo.git or 
                     sudo chown -R dyo:team perpelabuhan.git << success!!
                     
                      
FROM UBUNTU CONNECT TO SERVER
-----------------------------
    https://help.ubuntu.com/stable/ubuntu-help/nautilus-connect.html#urls              


ADD USER TO UBUNTU
------------------
    adduser nitza
    pass: nitza123
    
ADD USER TO GROUP SUDO
----------------------
    gpasswd -a nitza sudo
    
DOWNLOAD / COPY FILE FROM server to local
----------------------------------
    write this from destination to source remote    
    scp myusername@university_computer:/home/myusername/file.odt /local/destination/path/
    scp dyo@pengembanganpelabuhan.com:/home/dyo/perpelabuhan_dev_bkup.sql /home/dyo/Documents (form server to local)
    
    COPY TO ORDER SERVER
    --------------------
        scp dyo@widyobumi.com:/home/dyo/perpelabuhan_dev_bkup.sql dyo@pengembanganpelabuhan.com:/home/dyo/
    
Copy or cp
----------

Copy folder

[cp -r](http://askubuntu.com/questions/35779/what-does-cp-omitting-directory-mean)

## Create FTP

[Create ftp](https://www.digitalocean.com/community/questions/how-can-i-create-ftp-user-account-how-to-point-documentroot-var-www-html)            


## Lets try my another notes

### DOWNLOAD or COPY FILE from server to local or local to server Ubuntu

#### The Command

    scp myusername@university_computer:/home/myusername/file /local/destination/path/
    
    scp dyo@pengembanganpelabuhan.com:/home/dyo/perpelabuhan_dev_bkup.sql /home/dyo/Documents (form server to local)
    
#### Copy to other server
   
    scp dyo@widyobumi.com:/home/dyo/perpelabuhan_dev_bkup.sql dyo@pengembanganpelabuhan.com:/home/dyo/

## Problem install ubuntu 14.04

serious error were found while checking the disk drive for /

Solutions:

    In Windows Boot Manager, select Ubuntu.
    Press any key and enter GNU Grub2 menu.
    You can press "e" to edit GRUB2 boot entry.
    You need to change the GRUB2 boot entry from "ro" to "rw",

    e.g.

    linux   /boot/vmlinuz-3.13.0-24-generic root=UUID=AAC884AC1F144321 loop=/ubuntu/disks/root.disk ro   quiet splash $vt_handoff
    to

    linux   /boot/vmlinuz-3.13.0-24-generic root=UUID=AAC884AC1F144321 loop=/ubuntu/disks/root.disk rw   quiet splash $vt_handoff
    Press F10, you can boot in Ubuntu 14.04.
    
and you can fix GRUB2 boot entry:

    sudo vi /etc/grub.d/10_lupin
    Change the line:

    linux   ${rel_dirname}/${basename} root=${LINUX_HOST_DEVICE} loop=${loop_file_relative} ro ${args}
    to:

    linux   ${rel_dirname}/${basename} root=${LINUX_HOST_DEVICE} loop=${loop_file_relative} rw ${args}
    Regenerate GRUB2 boot entry:

    sudo update-grub

 Reference: [askubuntu.com](http://askubuntu.com/questions/453411/ubuntu-14-04-not-booting-after-error-message-tmp-could-not-be-mounted)


    