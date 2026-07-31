# 90-Day DevOps Engineer Learning Plan

## Commitment Statement
I am fully committed to becoming a DevOps Engineer within the next 90 days. I will dedicate **6-hours daily** to hands-on learning, building projects, and documenting my progress. This plan reflects my discipline, consistency, and focus.

---
# 🐧 Learn Linux in 14 Days

A simple, day-by-day plan to learn Linux. Each day has:
- **What you'll learn** (short and simple)
- **What you'll practice** (typing real commands)

No jargon overload — just learn a little, then do a lot.

---

## How to use this

1. Do one day at a time. Don't rush.
2. Type every command yourself. Don't copy-paste.
3. Check the box ✅ when you finish a day.
4. If something breaks — that's normal! Try to fix it, that's how you learn.

**You need:** Any Linux system — Ubuntu on a VM, WSL2 on Windows, or a cloud server. Ubuntu is easiest for beginners.

---

## ✅ Track Your Progress

- [ ] Day 1 - Moving around & files
- [ ] Day 2 - Reading & writing files
- [ ] Day 3 - Permissions (who can do what)
- [ ] Day 4 - Users & sudo
- [ ] Day 5 - Processes (running programs)
- [ ] Day 6 - Pipes & filtering text
- [ ] Day 7 - Find & replace text (grep, sed, awk)
- [ ] Day 8 - Installing software
- [ ] Day 9 - Internet & network basics
- [ ] Day 10 - Disk space & monitoring
- [ ] Day 11 - Writing your own scripts
- [ ] Day 12 - Scheduling tasks automatically
- [ ] Day 13 - Logs & fixing problems
- [ ] Day 14 - Final project

---

## Day 1 – Moving Around & Files

**Learn:** Linux stores everything in folders, starting from `/`. You move around using a few basic commands.

**Practice:**
- [ ] `pwd` – show where you are
- [ ] `ls -la` – list files (even hidden ones)
- [ ] `cd foldername` – move into a folder
- [ ] `mkdir myfolder` – make a folder
- [ ] `touch file.txt` – create an empty file
- [ ] `cp`, `mv`, `rm` – copy, move, delete files
- [ ] **Try this:** make a folder called `practice`, go inside it, create 3 files, then delete one

---

## Day 2 – Reading & Writing Files

**Learn:** You can view file contents without opening a full editor.

**Practice:**
- [ ] `cat file.txt` – show the whole file
- [ ] `less file.txt` – scroll through a file (press `q` to quit)
- [ ] `head file.txt` – show first 10 lines
- [ ] `tail file.txt` – show last 10 lines
- [ ] `tail -f file.txt` – watch a file update live
- [ ] `nano file.txt` – simple text editor (easy to use)
- [ ] **Try this:** open `/var/log/syslog`, view just the last 20 lines

---

## Day 3 – Permissions (Who Can Do What)

**Learn:** Every file has an owner and rules about who can read, write, or run it.

**Practice:**
- [ ] `ls -l` – see permissions on files
- [ ] `chmod +x script.sh` – make a file runnable
- [ ] `chmod 755 file.txt` – set exact permissions (numbers)
- [ ] `chown user file.txt` – change who owns a file
- [ ] **Try this:** create a file, remove all permissions with `chmod 000`, try to open it, then fix it back

---

## Day 4 – Users & Sudo

**Learn:** Linux supports many users. `sudo` lets a normal user run admin commands safely.

**Practice:**
- [ ] `whoami` – show your username
- [ ] `sudo adduser bob` – create a new user
- [ ] `sudo passwd bob` – set their password
- [ ] `su - bob` – switch to that user
- [ ] `groups` – see what groups you belong to
- [ ] **Try this:** create a new user and give them sudo access

---

## Day 5 – Processes (Running Programs)

**Learn:** Every running program is a "process" with an ID number. You can pause, resume, or stop them.

**Practice:**
- [ ] `ps aux` – list running processes
- [ ] `top` or `htop` – see live usage (press `q` to quit)
- [ ] `kill 1234` – stop a process by its ID
- [ ] `command &` – run something in the background
- [ ] **Try this:** open `htop`, find the process using the most memory, and note its name

---

## Day 6 – Pipes & Filtering Text

**Learn:** You can send the output of one command into another using `|` (pipe). This is one of the most powerful Linux tricks.

**Practice:**
- [ ] `cat file.txt | grep "error"` – find lines with "error"
- [ ] `cat file.txt | sort` – sort lines alphabetically
- [ ] `cat file.txt | wc -l` – count lines
- [ ] `command > output.txt` – save output to a file
- [ ] **Try this:** find how many times the word "error" appears in a log file

---

## Day 7 – Find & Replace Text

**Learn:** Three tools help you search and edit text quickly: `grep` (search), `sed` (replace), `awk` (pick columns).

**Practice:**
- [ ] `grep "word" file.txt` – search for a word
- [ ] `grep -i "word" file.txt` – search, ignore uppercase/lowercase
- [ ] `sed 's/old/new/g' file.txt` – replace "old" with "new"
- [ ] `awk '{print $1}' file.txt` – print just the first word of each line
- [ ] **Try this:** replace every "cat" with "dog" in a text file using `sed`

---

## Day 8 – Installing Software

**Learn:** Ubuntu uses `apt` to install and remove software easily.

**Practice:**
- [ ] `sudo apt update` – refresh the list of available software
- [ ] `sudo apt install nginx` – install a program
- [ ] `apt list --installed` – see what's installed
- [ ] `sudo apt remove nginx` – uninstall it
- [ ] **Try this:** install `nginx`, check it's running, then remove it completely

---

## Day 9 – Internet & Network Basics

**Learn:** A few simple commands let you check your connection and talk to other computers.

**Practice:**
- [ ] `ip a` – show your IP address
- [ ] `ping google.com` – check if you can reach the internet
- [ ] `curl https://example.com` – fetch a webpage from the terminal
- [ ] `sudo ufw enable` – turn on the firewall
- [ ] **Try this:** run `python3 -m http.server 8080`, then open it in a browser at `localhost:8080`

---

## Day 10 – Disk Space & Monitoring

**Learn:** Keep track of how much space and memory your system is using.

**Practice:**
- [ ] `df -h` – see disk space per drive
- [ ] `du -sh foldername` – see how big a folder is
- [ ] `free -h` – see memory usage
- [ ] **Try this:** find the 5 biggest files or folders on your system

---

## Day 11 – Writing Your Own Scripts

**Learn:** A script is just a text file full of commands that run one after another.

**Practice:**
- [ ] Create a file `myscript.sh`, start it with `#!/bin/bash`
- [ ] Add a few commands, save it, run `chmod +x myscript.sh`, then run it with `./myscript.sh`
- [ ] Use a variable: `name="Linux"` then `echo "Hello $name"`
- [ ] Use a loop:
  ```bash
  for i in 1 2 3
  do
    echo "Number: $i"
  done
  ```
- [ ] **Try this:** write a script that prints today's date and lists files in the current folder

---

## Day 12 – Scheduling Tasks Automatically

**Learn:** You can tell Linux to run a script automatically at certain times using `cron`.

**Practice:**
- [ ] `crontab -e` – open your schedule file
- [ ] Add a line to run a script every 5 minutes:
  ```
  */5 * * * * /home/youruser/myscript.sh
  ```
- [ ] Check it worked by looking at a log file it creates
- [ ] **Try this:** schedule your Day 11 script to run every 5 minutes and confirm it works

---

## Day 13 – Logs & Fixing Problems

**Learn:** When something goes wrong, logs tell you what happened.

**Practice:**
- [ ] `journalctl -xe` – view recent system logs
- [ ] Look inside `/var/log` for interesting files
- [ ] **Try this:** stop a running service on purpose, then use logs to figure out what's wrong and start it again

---

## Day 14 – Final Project

**Put it all together.** Build this small project using everything you've learned:

- [ ] Create a new user with no admin rights
- [ ] Write a script that checks disk space and saves the result to a log file
- [ ] Schedule that script to run every 10 minutes using cron
- [ ] Make sure only you and the new user can read the log file
- [ ] Write a short `README.md` explaining what your project does

---

## 🔧 Cheat Sheet (Most-Used Commands)

```
ls, cd, pwd, mkdir, cp, mv, rm       → files & folders
cat, less, head, tail, nano         → viewing/editing files
chmod, chown                        → permissions
sudo, adduser, su                   → users & admin
ps, top, kill                       → running programs
grep, sed, awk, sort                → searching & editing text
apt install/remove                  → software
ip, ping, curl, ufw                 → network
df, du, free                        → disk & memory
crontab                             → scheduling
journalctl                          → logs