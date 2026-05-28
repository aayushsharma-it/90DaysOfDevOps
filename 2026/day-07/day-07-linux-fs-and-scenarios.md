# Day 07 – Linux File System Hierarchy & Scenario-Based Practice

## Part 1: Linux File System Hierarchy

 ### 1. / (Root Directory)

 Root directory is the starting point of Linux.
 Everything in Linux starts from /.

 Command :

 ls -l /

 I would use this when...

 I want to understand the Linux file structure.

 ### 2. /home

 Stores normal user home directories.

 Every user gets their own folder here.

 Command :

 ls -l /home

 I would use this when...

 I want to access user files and folders.

 ### 3. /root

 Home directory of root user.

 Used for administrative work.

 Command :

 sudo ls -l /root

 I would use this when...

 I work as root/admin user.

 ### 4. /etc

 Stores configuration files.

 Important for Linux and services configuration.

 Command:

 ls -l /etc

 Example Files:

 hostname

 passwd

 I would use this when...

 I need to change system or service configuration.

 ### 5. /var/log

 Stores system and application log files.

 Very important for troubleshooting.

 Command:

 ls -l /var/log

 Example Files:

 syslog

 auth.log

 I would use this when...

 I need to debug server or application issues.

 ### 6. /tmp

 Stores temporary files.

 Files may get deleted after reboot.

 Command:

 ls -l /tmp

 I would use this when...

 I need temporary storage while testing.

## Additional Directories

 ### 7. /bin

 Contains essential Linux commands.

 Command:

 ls /bin

 Example Commands:

 ls

 cp

 I would use this when...

 I want to know where system commands are stored.

 ### 8. /usr/bin

 Stores installed user commands and applications.

 Command:

 ls /usr/bin

 Example Commands:

 git

 python3

 I would use this when...

 I want to check installed applications.

## Hands-on Practice

 ### Find Largest Log Files

 Command:

 sudo du -sh /var/log/* | sort -h | tail -5

 What I Learned

 This command helps identify large log files using storage.

 ### Check Hostname File

 Command:

 cat /etc/hostname

 What I Learned

 This file stores the system hostname.

 ### Check Home Directory

 Command:

 ls -la ~

 What I Learned

 Shows all files including hidden files in home directory.

## Part 2: Scenario-Based Practice

## Scenario 1: Service Not Starting

 ### Problem:

 A ssh service failed after reboot.

 ### Step 1: Check Service Status

 systemctl status ssh

 Why:

 Checks whether the service is running or failed.

 ### Step 2: Check Service Logs

 journalctl -u ssh -n 50

 Why:

 Shows last 50 log lines for troubleshooting.

 ### Step 3: Check Boot Enable Status

 systemctl is-enabled ssh

 Why:

 Checks whether service starts automatically after reboot.

## Scenario 2: High CPU Usage

 ### Problem:

 Server is running slow.

 ### Step 1: Check Live CPU Usage

 top

 Why:

 Shows live CPU and memory usage.

 ### Step 2: Find Top CPU Processes

 ps aux --sort=-%cpu | head -10

 Why:

 Shows highest CPU consuming processes.

 ### Step 3: Process Mitigation

 sudo renice +10 -p PID

 Why:

 lower the process priority to stop the server from lagging. This buys you time to investigate without crashing the system.

 ### Step 4: Kill Process

 kill -9 PID

 Why:

 To stop frozen, resource-hogging processes and restore server stability.

## Scenario 3: Finding Service Logs

 ### Problem:

 Developer asks for SSH service logs.

 ### Step 1: Check SSH Service Status

 systemctl status ssh

 Why:

 Checks whether SSH service is running.

 ### Step 2: View Last 50 Logs

 journalctl -u ssh -n 50

 Why:

 Shows recent SSH logs.

 ### Step 3: Follow Logs in Real Time

 journalctl -u ssh -f

 Why:

 Displays logs live.

## Scenario 4: File Permission Issue

 ### Problem:

 Script is showing "Permission denied"

 ### Step 1: Create Script File

 echo 'echo "Backup Started Successfully"' > backup.sh

 Why:

 Creates script with valid Linux command.

 ### Step 2: Check Script Content

 cat backup.sh

 Output:

 echo "Backup Started Successfully"

 Why:

 Verifies script content.

 ### Step 3: Check Current Permissions

 ls -l backup.sh

 Look for:

 -rw-rw-r--

 Why:

 Shows file is not executable yet.

 ### Step 4: Add Execute Permission

 chmod +x backup.sh

 Why:

 Makes script executable.

 ### Step 5: Verify Permissions

 ls -l backup.sh

 Look for:

 -rwxrwxr-x

 Why:

 Confirms execute permission is added.

 ### Step 6: Run the Script

 ./backup.sh

 Output:

 Backup Started Successfully

 Why:

 Executes the script successfully.

## What I Learned Today

Linux follows a structured file system hierarchy.

/etc stores configuration files.

/var/log stores important logs.

systemctl and journalctl help troubleshoot services.

top and ps help identify high CPU usage.

chmod +x makes a script executable.