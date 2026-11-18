# Linux Practice – Process and systemd Troubleshooting

**Date:** 18 November 2026  
**OS:** Ubuntu   
**Service inspected:** cron  
**Objective:** Practice Linux process monitoring, systemd service inspection, and log analysis.

## 1. Process checks

### Command 1: List running processes

```bash
ps aux | head -10
```

**Purpose:** Display running processes.

**Actual output (representative):**

```text
USER         PID %CPU %MEM    VSZ   RSS TTY STAT COMMAND
root           1  0.0  1.7  25500 16248 ?   Ss   /sbin/init
root           2  0.0  0.0      0     0 ?   S    [kthreadd]
root           3  0.0  0.0      0     0 ?   I    [pool_workqueue_release]
```

**Observation:**
- PID 1 is `/sbin/init`.
- Kernel threads are visible.
- Process information is displayed successfully.

### Command 2: Find cron process

```bash
pgrep -a cron
```

**Purpose:** Find the cron process and its PID.

**Actual output:**

```text
585 /usr/sbin/cron -f -P
```

**Observation:**
- Cron process is running.
- Process ID is 585.
- Executable is `/usr/sbin/cron`.

## 2. Service checks

### Command 3: Inspect cron service

```bash
systemctl status cron --no-pager
```

**Purpose:** Check whether cron is active or failed.

**Actual output (important fields):**

```text
cron.service - Regular background program processing daemon

Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled)
Active: active (running)

Main PID: 585 (cron)
Tasks: 1
Memory: 528K
CPU: 43ms
```

**Observation:**
- Cron service is active and running.
- Service is enabled at boot.
- Main PID is 585.
- Systemd PID matches the pgrep result.

### Command 4: List running services

```bash
systemctl list-units --type=service --state=running
```

**Purpose:** Identify currently running system services.

**Actual output (selected entries):**

```text
acpid.service        loaded active running
chrony.service       loaded active running
cron.service         loaded active running
dbus.service         loaded active running
irqbalance.service   loaded active running
rsyslog.service      loaded active running
ssh.service          loaded active running
snapd.service        loaded active running
```

**Observation:**
- Cron is listed as running.
- SSH service is running.
- Chrony and rsyslog are also running.
- Total running service units listed: 24.

## 3. Log checks

### Command 5: Inspect cron logs

```bash
sudo journalctl -u cron -n 20 --no-pager
```

**Purpose:** Identify recent cron service events and errors.

**Actual output (selected entries):**

```text
Nov 18 10:37:22 systemd[1]: Started cron.service

Nov 18 10:37:22 (cron)[585]:
Referenced but unset environment variable:
EXTRA_OPTS

Nov 18 10:37:22 cron[585]:
(CRON) INFO (pidfile fd = 3)

Nov 18 10:37:22 cron[585]:
(CRON) INFO (Running @reboot jobs)

Nov 18 11:17:01 CRON[1833]:
(root) CMD (cd / && run-parts --report /etc/cron.hourly)
```

**Observation:**
- Cron service started successfully.
- Hourly cron job runner was invoked.
- An unset EXTRA_OPTS environment variable warning appeared.
- No service failure is shown in these entries.

### Command 6: Inspect system warnings

```bash
sudo journalctl -p warning -n 20 --no-pager
```

**Purpose:** Identify recent system warnings.

**Actual output (selected entries):**

```text
kernel: MMIO Stale Data CPU bug present and SMT on

acpid.service:
Referenced but unset environment variable: OPTIONS

cron.service:
Referenced but unset environment variable: EXTRA_OPTS

irqbalance.service:
Referenced but unset environment variable: IRQBALANCE_ARGS

chronyd:
System clock wrong by 1.396807 seconds

sshd-session:
Connection reset by peer
```

**Observation:**
- Multiple system warnings were identified.
- Cron has an unset environment variable warning.
- SSH experienced a connection reset.
- These warnings do not establish that cron has failed.

## 4. Mini troubleshooting steps

1. Check service status using `systemctl status`.
2. If the service has failed, inspect its logs.
3. Identify the error message.
4. Investigate the root cause.
5. Fix the issue if necessary.
6. Restart the service only when appropriate.
7. Verify service status again.

**Practice status:** Completed.
