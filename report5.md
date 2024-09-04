## Managing Processes in Linux

1. **Process Status `ps [options]`**

      _displays a snapshot of currently running processes, provides various details about 
the processes, depending on the options used_
   
      Common Options:
   
      - `-aux` displays all processes for all users, along with detailed information
      - `-ef` displays all processes with more details

      Examples:
    - `ps aux` displays all running processes
    - `ps -e --forest` displays processes in a tree format (shows parent-child relationships)
    - `ps -u username` displays processes filtered by user
    - `ps -p 1234` display processes by their PID (Process ID)


2. **Task Manager `top`**

      _is an interactive command-line tool that provides a real-time view of the running system, including CPU usage,
   memory usage, and process information; allows you to monitor system resource usage and manage processes_
   
      Interactive Commands (inside top):
   
      - `h` display help
      - `k` Kill a process by entering its PID
      - `q` quit top
      - `u` filter by username
      - `M` sort processes by memory usage
      - `P` sort processes by CPU usage


3. **Interactive Process Viewer `htop`**

      _is an enhanced version of `top` with a more user-friendly, colorful, and interactive interface; provides a 
   more detailed and customizable view of system processes_

    Installation:
   - On Ubuntu/Debian: `sudo apt install htop`
   - On CentOS/RHEL: `sudo yum install htop`
   - On Fedora: `sudo dnf install htop`
   
   Interactive Commands (inside htop):
   - Arrow keys: navigate through processes
   - `F3`: Search for a process
   - `F4`: Filter processes
   - `F5`: Tree view (displays parent-child relationships)
   - `F6`: Sort processes by a specific column
   - `F9`: Kill a process
   - `F10`: Quit htop



4. **Terminate Processes `kill [options] PID`**

      _to send signals to processes, most commonly to terminate them. You can specify the signal type and the PID of 
   the process to be killed_

    Common Signals:
   - `SIGTERM (15)`: Politely asks a process to terminate (default signal)
   - `SIGKILL (9)`: Forcefully terminates a process
   - `SIGSTOP`: Pauses a process
   - `SIGCONT`: Resumes a paused process
   
   Examples:
   - `kill 1234` terminate a process using its PID
   - `kill -9 1234` forcefully kill a process
   - `kill -SIGSTOP 1234` pause a process
   - `kill -SIGCONT 1234` resume a paused process



5. **Terminate Multiple Processes `killall [options] process_name`**

      _sends signals to all processes running with a specified name. It’s useful for stopping all instances of a program_
 
    Examples:
   - `killall firefox` kill all instances of the firefox process
   - `killall -9 firefox` Forcefully kill all instances of a process




6. **Terminate Processes by Name `pkill [options] pattern`**

      _sends signals to processes based on a name pattern, similar to `killall`, but with more flexible matching options_

    Examples:
   - `pkill fire` kill processes matching the pattern fire
   - `pkill -u username` Kill processes matching a specific user



7. **Display Memory Usage `free [options]`**

      _displays the amount of free and used memory in the system_

    Common Options:
   - `-h` display sizes in human-readable format (e.g., MB, GB)

   Example: `free -h`



8. **System Uptime and Load Average `uptime`**

      _displays how long the system has been running, the number of users, and the system load averages_

    Example Output:
        
        14:35:42 up  2:25,  1 user,  load average: 0.10, 0.20, 0.15


9. **Disk Space Usage `df [options]`**

      _df reports the amount of disk space used and available on filesystems_

    Common Signals:
   - `-h` display sizes in human-readable format (e.g., MB, GB)
   
   Examples:
   - `df -h`
   