# Linux Practice - Processes and Services

## Process Checks

### Process Command 1 

Shows all running processes in the system.

Command:
ps aux

Run:

![alt text](images/ps.png)

### Process Command 2

Displays live CPU and memory usage.

Command:
top

Run:

![alt text](images/top.png)

## Service Checks

### Service Command 1

Used to inspect whether SSH service is active or not.

Command:
systemctl status ssh

Run:

![alt text](images/s1.png)

### Service Command 2

Shows all active services running on the system.

Command:
systemctl list-units --type=service

Run:

![alt text](images/s2.png)

## Log Checks

### Log Command 1

Displays logs related to SSH service.

Command:
journalctl -u ssh

Run :

![alt text](images/l1.png)

### Log Command 2

Shows the latest 50 lines from system logs.

Command:
tail -n 50 /var/log/syslog

Run:

![alt text](images/l2.png)

## Mini Troubleshooting

### Problem

SSH service was not responding properly.

### Steps Performed
1. Checked running processes using "ps aux"
2. Verified SSH service status using "systemctl status ssh"
3. Reviewed logs using "journalctl -u ssh"
4. Confirmed service was active and running
### Learning

Learned how to inspect processes, services, and logs in Linux.