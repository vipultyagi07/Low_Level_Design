# RESET MySQL password without old password

The steps below show how to reset the MySQL root password in Windows, we will use Windows 11, but the process works for Windows 10 as well.


## Step 1: Stop MySQL server
1. Press **Win+R** (hold the Windows/Super key, and press r).

2. In the Run box, type **services.msc** and press Enter.
    Find MySQL in the list then press right click and click on the **STOP**

## Step 2: Create Password File
   Open Notepad then write this **ALTER USER 'root'@'localhost' IDENTIFIED BY 'NewPassword';**
   ![see](https://github.com/vipultyagi07/Low_Level_Design/blob/main/Zzzzz/mysql-init.png)

   Save the file to the root of your hard drive (C: ). The filename should be **mysql-init.txt**  --> name should be same
     (when you directly save file to C: drive it may not allowed so it is better to save it somewhere else, then copy it to directly C: drive)

   ![see](https://github.com/vipultyagi07/Low_Level_Design/blob/main/Zzzzz/folderOne.png)

## Step 3: Open Command Prompt
1. Press the Windows key and type cmd.

2. From the search results, select the Run as administrator option to open Command Prompt as administrator.
   ![see](https://github.com/vipultyagi07/Low_Level_Design/blob/main/Zzzzz/cmd.png)

## Step 4: Add New Parameters and Restart Server
 1. Navigate to the MySQL directory using the command prompt:
**cd "C:\Program Files\MySQL\MySQL Server 5.7\bin"**   
 --> instead of 5.7 find your mysql version in C:\Program Files\MySQL and rplace
 2. Depending on how you installed MySQL, there are two ways to restart the server with the new parameters:

    ### If you installed MySQL using the MySQL Installation Wizard  -- use this 
    **mysqld --defaults-file="C:\\ProgramData\\MySQL\\MySQL Server 5.7\\my.ini" --init-file=C:\\mysql-init.txt**

    --> instead of 5.7 find your mysql version in C:\Program Files\MySQL and rplace

    ### If you installed MySQL using the ZIP archive
    **mysqld --init-file=C:\\mysql-init.txt**

   ## Step 5: Clean up
Now, log into your MySQL server as root using the new password. Once MySQL launches and you've confirmed the password change, delete the **C:\mysql-init.txt** file.






     
      
   


