
# Day 02 - Linux Architecture, Processes, and systemd

## Linux Architecture

Linux architecture is divided into 4 main layers:

Hardware → Kernel → Shell → Applications

### 1. Hardware
Physical components of the computer:
- CPU
- RAM
- Hard Disk
- Keyboard
- Network devices

### 2. Kernel (Heart of Linux)
The kernel is the core part of Linux.

Responsibilities:
- Process management
- Memory management
- Device management
- File system handling
- CPU scheduling

The kernel directly communicates with hardware.

### 3. Shell
Shell acts as a bridge between the user and kernel.

Examples:
- bash
- sh
- zsh

When users type commands, the shell sends requests to the kernel.

Example:
ls
pwd


### 4. Applications / User Space
Applications used by users:

- VS Code
- Docker
- Terminal

Applications run in user space and interact with the kernel through the shell.

---

# Linux Processes

## What is a Process?
A process is a running instance of a program.

Each process has:
- PID (Process ID)
- Memory usage
- CPU usage

---

# Process States

| State | Meaning |
|---|---|
| Running | Process is executing |
| Sleeping | Waiting for input/resource |
| Stopped | Process paused |
| Zombie | Process completed but entry still exists |

---

# systemd

## What is systemd?
systemd is the service manager in Linux.

It is the first process started during boot and has PID 1.

Responsibilities:
- Starts system services
- Restarts failed services
- Manages background processes
- Handles boot process


---

# 5 Daily Linux Commands

ps aux
top
free -m
df -h


### Command Usage
- `ps aux` → Show running processes
- `top` → Live system monitoring
- `free -m` → Check memory usage
- `df -h` → Check disk usage


---

# What I Learned

- Linux architecture contains Hardware, Kernel, Shell, and Applications
- Kernel is the heart of Linux
- Processes are important for system operations
- systemd manages Linux services efficiently
- Linux commands help monitor and troubleshoot systems

