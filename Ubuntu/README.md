# Ubuntu 14.04


remove directory
----------------
sudo rm -r -f /path/


HOW TO ADD A USER TO A GROUP IN UBUNTU 14.04
============================================
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
    

            