# Linux `Commands` for Working with Files and Directories

1. **Print Working Directory `pwd`** 
    
    _displays the current directory you are working in_


2. **Change Directory `cd path/to/directory`**

    _changes the current directory to the specified path_

    Examples:
   - Go to the home directory: `cd ~`
   - Go up one directory: `cd ..`


3. **List `ls [options] [path]`** 
    
    _lists files and directories in the current directory_
    
    Common Options (flags):

    `-l` long format listing (shows detailed information).

    `-a` lists all files, including hidden files (those starting with .).

    `-h` displays file sizes in human-readable format (e.g., KB, MB).

    Example: `ls -alh /home/user`


4. **Create Empty File `touch filename`**
    
    _creates an empty file or updates the timestamp of an existing file_


5. **Make Directory `mkdir directory_name`**

    _creates a new directory_
    
    Common Options (flags):

    `mkdir -p folder1/folder2/folder3` create nested directories


6. **Copy `cp [options] source destination`** 

    _copies files or directories from one location to another_

    Common Options (flags):

    `-r` recursively copy directories and their contents

    `-i` prompts before overwriting files

    `-u` only copies when the source file is newer than the destination file or when the destination file is missing

   Examples:
   - `cp file.txt /home/user/Documents/` copy file.txt to /home/user/Documents/
   - `cp -r /home/user/old_directory /home/user/new_directory` copy /home/user/old_directory to 
     /home/user/new_directory
   
      
7. **Move `mv [options] source destination`**
    
    _moves or renames files and directories_

    Examples:

    - `mv file.txt /home/user/Documents/` move a file to a different directory
    - `mv oldname.txt newname.txt` rename a file


8. **Remove/remove directory `rm [options]`**

    _deletes files or directories_
    
    Common Options:
   
   `-r` recursively delete directories and their contents

   `-i` prompts before every removal

   `-f` force deletion without prompts
   
   Examples:
   - `rm file.txt` deletes the file
   - `rm -r directory_name` deletes the directory and its contents


9. **Remove Directory `rmdir directory_name`**

   _deletes an empty directory_


10. **Concatenate and Display File Content `cat filename`**

      _displays the content of a file_


11. **View File Content One Screen at a Time `less filename`**

      _allows you to view file content one screen at a time, with the ability to scroll_


12. **Display the First Lines of a File `head filename`**

      _displays the first 10 lines of a file by default or a specific number of lines if like `head -n 20 file.txt`_


13. **Display the Last Lines of a File `tail [options] filename`**

      _displays the last 10 lines of a file by default_
   
      Options:
   
      `-f` follow file for new content (useful for logs)


14. **Search for Files and Directories `find path [options] [expression]`**

      _searches for files and directories within a specified directory hierarchy_
   
      Examples:
      - `find /home/user -name "file.txt"` find a file by name
      - `find . -name "*.txt"` find all .txt files in the current directory and subdirectories


15. **Search Inside Files `grep [options] pattern filename`**
   
      _searches for a specific pattern within files_
      
      Examples:
      - `grep "word" file.txt` search for a specific word in a file
      - `grep -r "word" /path/to/directory` search recursively within a directory:


16. **Change File Permissions `chmod [options] mode filename`**
    
      _changes the permissions of a file or directory_
      
      Example: `chmod +x script.sh` make a file executable


17. **Change File Ownership `chown [options] owner[:group] filename`**
    
      _changes the owner and/or group of a file or directory_
    
      Examples:
      - `chown user file.txt` change the owner of a file
      - `chown -R user:group directory_name` change the owner and group of a directory
 
