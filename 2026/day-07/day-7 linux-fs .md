ps-aux : It shows every single process running on the machine
--sort=-%cpu : Instructs the utility to sort the resulting list based on the %CPU usage column.

### Hands-on Task Outputs

1. Find the largest log file in /var/log:
     \$ du -sh /var/log/* 2>/dev/null | sort -h | tail -5

2. Look at a config file in /etc:
   \$ cat /etc/hostname
  

3. Check your home directory:
   \$ ls -la ~


## Part 2: Scenario-Based Practice

### Scenario 1: Service Not Starting
* Problem Statement: A web application service called myapp failed to start after a server reboot. Diagnose the issue.

* Step 1: systemctl status myapp
  * Why: To review the overall active execution condition of the service daemon, check the error code exit parameters, and grab the first few structural startup logs.
* Step 2: journalctl -u myapp -n 50 --no-pager
  * Why: To drill down into the last 50 historical entries logged specifically by this systemd unit to isolate missing dependencies, file access bugs, or compilation crashes.
* Step 3: systemctl is-enabled myapp
  * Why: To discover if the daemon is currently configured to boot up automatically when the node reboots. If it responds as disabled, this explains why it did not fire up.
* Step 4: sudo systemctl enable --now myapp
  * Why: To fix the root boot configuration gap by locking it into systemd's default startup schedules while simultaneously firing up the operational service layer right away.

---

### Scenario 2: High CPU Usage
* Problem Statement: The application server is reporting slow response cycles. SSH into the server and locate the problem process.

* Step-by-step Solution:
  * Step 1: Execute a quick sorted snapshot to capture top consumers without interactive lag:
    ```bash
    ps aux --sort=-%cpu | head -10
    ```
    * Why: This immediately lists the top processes taking up compute cycles, highlighting their User owner, Process ID (PID), and precise CPU utilization percentage.
  * Step 2: Launch interactive analysis to trace active shifts:
    ```bash
    top -b -n 1
    ```
    * Why: Confirms overall system health metrics (like load average trends over 1, 5, and 15 minutes) and updates the top rows to catch rapid performance swings.
  * Step 3: Note key metrics for mitigation:
    * Identified Process: python3 data_processor.py
    * Target PID: 4821
    * Resource Usage: Consuming 94.2% CPU. This clearly indicates an unoptimized thread or infinite loop block causing server slowdowns.

---

### Scenario 3: Finding Service Logs
* Problem Statement: A developer needs to locate and trace runtime system log entries for the docker service managed under systemd.

* Step-by-step Solution:
  * Step 1: Verify the active runtime identity of the docker configuration setup:
    ```bash
    systemctl status docker
    ```
    * Why: Confirms the exact name of the underlying service unit and lets you see its active uptime metrics and process configurations.
  * Step 2: Retrieve the final 50 logs cleanly onto the terminal prompt:
    ```bash
    journalctl -u docker -n 50 --no-pager
    ```
    * Why: Extracts a concise baseline layout of modern application history logs handled by journald without trapping you inside an interactive text editor window.
  * Step 3: Stream live streaming updates from the daemon process layer:
    ```bash
    journalctl -u docker -f
    ```
    * Why: Continuously streams real-time console entries to the screen. This allows the developer to test container launches or configuration updates and instantly see the system's reaction.


### Scenario 4: File Permissions Issue
* Problem Statement: A pipeline backup script located at /home/user/backup.sh throws an un-executable "Permission denied" error when run.

* Step-by-step Solution:
  * Step 1: Check current permissions

    ls -l /home/user/backup.sh

