# Linux Architecture, Processes & systemd — Day 02 Notes

## Core Components of Linux

* **Kernel** — The core of the Linux operating system. It communicates directly with the hardware (CPU, memory, disk, and network), manages system resources, and provides system calls for applications.
* **User Space** — The area where users interact with the system. It includes applications, shells (Bash), utilities, and services. Programs in user space cannot access hardware directly; they communicate through the kernel.
* **Init / systemd** — The first process started by the kernel during boot (PID 1). It initializes the system and manages all background services and processes.

**Linux Boot Flow**

`Hardware → Kernel → systemd (PID 1) → Services Start → User Space Ready`

---

## How Processes Are Created

* Every process begins from an existing process.
* A parent process creates a child process using **fork()**.
* The child process usually executes a new program using **exec()**.
* Every process has a unique **PID (Process ID)**.
* Every child process also has a **PPID (Parent Process ID)**.

---

## Process States

| State            | Description                                                                |
| ---------------- | -------------------------------------------------------------------------- |
| **Running (R)**  | Process is executing or ready to execute.                                  |
| **Sleeping (S)** | Waiting for an event or resource.                                          |
| **Stopped (T)**  | Process is paused or suspended.                                            |
| **Zombie (Z)**   | Process has finished but its parent has not yet collected its exit status. |

---

## What systemd Does

* Starts system services during boot.
* Stops, starts, and restarts services.
* Manages service dependencies.
* Automatically restarts failed services.
* Maintains system logs using **journalctl**.
* Helps monitor and troubleshoot production servers.

### Why systemd Matters

Most Linux servers use **systemd** to manage services. It allows administrators to monitor services, restart failed applications, and diagnose problems quickly.

---

## 5 Commands I'll Use Daily

1. `systemctl status <service>` — Check service status.
2. `ps aux` — Display running processes.
3. `top` or `htop` — Monitor CPU and memory usage.
4. `journalctl -u <service>` — View service logs.
5. `systemctl restart <service>` or `kill -9 <PID>` — Restart a service or terminate a process.

---

## Why This Matters

Understanding Linux architecture, processes, and systemd helps troubleshoot Linux servers effectively. By checking service status, viewing logs, monitoring processes, and restarting services when required, I can quickly identify and resolve issues. These are essential skills for every DevOps Engineer because Linux powers most production environments.
