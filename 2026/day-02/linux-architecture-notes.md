# Linux Architecture, Processes, and systemd

## Linux Architecture

Linux mainly consists of three core components:

### 1. Kernel
- Core part of the Linux operating system
- Manages CPU, memory, devices, filesystems, and processes
- Acts as a bridge between hardware and software

### 2. User Space
- Area where users and applications run
- Includes commands, applications, shells, and utilities
- Interacts with the kernel using system calls

### 3. Init / systemd
- First process started during boot (PID 1)
- Responsible for starting and managing services
- Handles logging, service monitoring, and system startup

---

## Process Management in Linux

A process is a running instance of a program.

### Process Creation Flow
- A process is created using `fork()`
- Child process gets a unique PID
- Programs are executed using `exec()`

### Common Process States

| State | Meaning |
|------|------|
| Running | Process is actively using CPU |
| Sleeping | Waiting for an event or resource |
| Stopped | Process paused manually |
| Zombie | Process finished but entry still exists |
| Orphan | Parent process terminated |

---

## What is systemd?

systemd is the modern Linux service manager used in most Linux distributions.

### Why systemd Matters
- Starts services automatically during boot
- Restarts failed services
- Manages background processes
- Provides centralized logging through `journalctl`
- Improves boot performance with parallel startup

---

## Useful Daily Linux Commands

- ps aux → View running processes 
- top → Monitor CPU and memory usage
- systemctl status → Check service status
- journalctl -xe → View system logs
- kill -9 PID → Force stop a process
