# How to manage users and group in Linux

1. **Add a New User `adduser`**
    
    _Adds a new user to the system with a home directory and initial settings_
    
    Example: `sudo adduser john` creates a new user named john, create a home directory (/home/john), and prompt you 
   to set a password and other optional information
    

2. **Add a New User `useradd [options] username`**

   _Adds a new user with more flexibility but less automatic setup than `adduser`_

    Example: `sudo useradd -m -s /bin/bash john` the -m option creates a home directory, and -s sets the default 
   shell for the user


3. **Modify an Existing User `usermod [options] username`**

   _Modifies a user account, including changing the user's group, home directory, shell, etc._

    Examples:

    - `sudo usermod -g groupname john` changes a user's primary group
    - `sudo usermod -aG groupname john` adds a user to an additional group
    - `sudo usermod -s /bin/zsh john` changes the user's shell
    - `sudo usermod -d /new/home/directory john` changes the user's home directory


4. **Delete a User `deluser [options] username`**

   _Deletes a user from the system, optionally removing the user's home directory and files_

    Examples:

    - `sudo deluser john` deletes a user
    - `sudo deluser --remove-home john` deletes a user and their home directory


5. **Delete a User `userdel [options] username`**

   _Another command to delete a user_

    Examples:

    - `sudo userdel john` deletes a user
    - `sudo userdel -r john` deletes a user and their home directory


6. **Add a New Group `groupadd groupname`**

   _Creates a new group on the system_

    Example: `sudo groupadd developers` creates a new group called developers


7. **Modify an Existing Group `groupmod [options] groupname`**

   _Modifies a group, such as renaming it or changing its GID (Group ID)_

    Example: `sudo groupmod -n newgroupname oldgroupname` renames a group


8. **Delete a Group `groupdel groupname`**

   _Deletes a group from the system_

    Example: `sudo groupdel developers` deletes the developers group


9. **Change File/Directory Permissions `chmod [options] mode filename`**

   _Changes the read, write, and execute permissions for files and directories_

    Examples:

      - `chmod 755 script.sh` sets read (r), write (w), and execute (x) permissions for the owner, and read and 
        execute permissions for the group and others
        - 7 (owner) = read + write + execute (4+2+1)
        - 5 (group) = read + execute (4+1)
        - 5 (others) = read + execute (4+1)
      - `chmod +x script.sh` adds execute permission for everyone


10. **Change File/Directory Ownership `chown [options] owner[:group] filename`**

      _Changes the read, write, and execute permissions for files and directories_

      Examples:
      - `sudo chown john file.txt` changes the owner of a file
      - `sudo chown -R john:developers /home/john` changes the owner and group of a directory, `-R`: Recursively 
        change ownership for all files and subdirectories within the specified directory


11. **Show User Groups `groups [username]`**

      _Displays the groups a user belongs to_

      Example: `groups john` shows all groups the user john is a member of


12. **Administer /etc/group `sudo gpasswd [options] groupname`**

      _Manages group membership, such as adding or removing users from groups_

      Examples:
      - `sudo gpasswd -a john developers` adds a user to a group
      - `sudo gpasswd -d john developers` removes a user from a group
