# 🐧 Linux Commands Cheat Sheet – Day 03

> A quick reference for essential Linux commands used in DevOps and System Administration.

---

## 📂 File System

### Show current directory
```bash
pwd
```
Displays the current working directory.

### List files
```bash
ls -la
```
Lists all files (including hidden files) with detailed information.

### Change directory
```bash
cd /path/to/directory
```
Moves to another directory.

### Create directory
```bash
mkdir project
```
Creates a new directory.

### Copy files
```bash
cp source.txt destination.txt
```
Copies a file.

### Move or Rename
```bash
mv old.txt new.txt
```
Moves or renames a file.

### Delete file
```bash
rm file.txt
```
Deletes a file.

### Find files
```bash
find . -name "*.log"
```
Searches for log files recursively.

---

## 📄 File Viewing & Logs

### Display file
```bash
cat file.txt
```
Prints file contents.

### View first lines
```bash
head file.txt
```
Shows first 10 lines.

### View last lines
```bash
tail file.txt
```
Shows last 10 lines.

### Monitor logs
```bash
tail -f /var/log/syslog
```
Displays logs in real time.

### Search text
```bash
grep "ERROR" app.log
```
Finds matching text in a file.

---

## ⚙️ Process Management

### Running processes
```bash
ps aux
```
Lists all running processes.

### Interactive process viewer
```bash
top
```
Shows CPU and memory usage.

### Kill process
```bash
kill PID
```
Terminates a process.

### Force kill
```bash
kill -9 PID
```
Forcefully stops a process.

### Kill by name
```bash
pkill nginx
```
Stops a process using its name.

---

## 🌐 Networking

### IP Address
```bash
ip addr
```
Shows network interfaces and IP addresses.

### Test connectivity
```bash
ping google.com
```
Checks network connectivity.

### Test API / Website
```bash
curl https://example.com
```
Sends an HTTP request.

### DNS Lookup
```bash
dig google.com
```
Retrieves DNS records.

### Open Ports
```bash
ss -tuln
```
Lists listening TCP/UDP ports.

---

## 💾 Disk Usage

### Disk space
```bash
df -h
```
Displays filesystem usage.

### Folder size
```bash
du -sh folder
```
Shows directory size.

### Memory usage
```bash
free -h
```
Displays RAM and swap usage.

---

## 🚀 Service Management

### Service status
```bash
systemctl status nginx
```
Checks the service status.

### Restart service
```bash
systemctl restart nginx
```
Restarts a service.

### Service logs
```bash
journalctl -u nginx
```
Displays service logs.

---

# ⭐ Most Used Commands

| Command | Purpose |
|---------|---------|
| `pwd` | Current directory |
| `ls -la` | List files |
| `grep` | Search text |
| `tail -f` | Live logs |
| `ps aux` | Running processes |
| `top` | Resource usage |
| `df -h` | Disk usage |
| `free -h` | Memory usage |
| `ip addr` | IP Address |
| `ping` | Connectivity |
| `curl` | API Testing |
| `systemctl` | Service Management |

---

## 🎯 DevOps Tip

When troubleshooting a Linux server, these commands are often enough to answer:

- Is the service running?
- Is the process alive?
- Are the logs showing errors?
- Is the server out of disk or memory?
- Is the network reachable?

Master these basics before moving on to Docker, Kubernetes, AWS, and Terraform.

---

**#90DaysOfDevOps | Day 03**
