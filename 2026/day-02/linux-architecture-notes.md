
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
=======
# Linux Architecture — Notes

## Core components
- Kernel: manages hardware, processes, memory, drivers, and the scheduler.
- User space: shells, libraries, daemons, and applications that run on top of the kernel.
- Init / systemd (PID 1): boots userspace services, manages units, handles shutdown/restarts, and controls cgroups and logging.

## How processes are created and managed
- Creation: a process typically `fork()`s to create a child, then the child calls `exec()` to run a new program.
- Each process has a PID, PPID, UID/GID, and entries in the kernel process table.
- The kernel scheduler (CFS on most distros) allocates CPU time; the kernel also manages memory and IO for processes.
- Resource control and isolation: cgroups (control groups) limit CPU/memory/io; namespaces provide isolation for containers.

## Process states (short)
- Running: process is executing on the CPU.
- Interruptible sleep (S): waiting for an event or IO, can be woken.
- Uninterruptible sleep (D): waiting in kernel (often IO); cannot be killed until it returns.
- Stopped (T): suspended (e.g., SIGSTOP or debugger stop).
- Zombie (Z): process has exited but parent hasn't `wait()`ed; keeps an entry in the process table.

## 5 commands I use daily
- `ps aux` — snapshot of current processes and owners.
- `top` (or `htop`) — live CPU/memory usage and process sorting.
- `systemctl status <service>` — check service state and recent status info.
- `journalctl -u <service>` — view systemd logs for a specific unit.
- `ss -tulpn` — list listening sockets, ports, and owning processes.


