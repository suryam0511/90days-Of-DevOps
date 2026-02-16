
## Part 1: Linux File System Hierarchy

ls -l /var/log
You may see: syslog, auth.log

I would use this when… troubleshooting system or service issues.

📁 /tmp
Purpose: Temporary files stored during runtime; cleared periodically.

Example:

ls -l /tmp
You may see: temporary session files.

I would use this when… storing temporary scripts or test files.

⭐ Additional Directories
📁 /bin
Purpose: Essential commands required for boot and basic operations.

Examples: ls, cp, cat

Use when… running critical system commands.

📁 /usr/bin
Purpose: Most user-level command binaries.

Examples: git, python, vim

Use when… running installed applications.

📁 /opt
Purpose: Optional or third-party software installations.

Examples: /opt/google/, /opt/docker/

Use when… managing external applications.

✅ Hands-On Tasks
🔍 Find largest log files
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
🔍 View hostname config
cat /etc/hostname
🔍 List home directory
ls -la ~

## Part 2: Scenario-Based Practice

🛠 Scenario 1: Service Not Starting
Step 1
systemctl status myapp


Why: Check if service failed or stopped.

Step 2
journalctl -u myapp -n 50


Why: View recent error logs.

Step 3
systemctl is-enabled myapp


Why: Check if it starts on boot.

Step 4
systemctl list-units --type=service | grep myapp


Why: Confirm service exists.

🛠 Scenario 2: High CPU Usage
Step 1
top


Why: View live CPU usage.

Step 2
ps aux --sort=-%cpu | head -10


Why: Show top CPU-consuming processes.

Step 3
htop


Why: Interactive process viewer (if installed).

🛠 Scenario 3: Finding Service Logs (docker)
Step 1
systemctl status docker


Why: Confirm service state.

Step 2
journalctl -u docker -n 50


Why: View recent logs.

Step 3
journalctl -u docker -f


Why: Monitor logs live.

🛠 Scenario 4: Permission Denied Script
Step 1
ls -l /home/user/backup.sh


Why: Check permissions.

Step 2
chmod +x /home/user/backup.sh


Why: Add execute permission.

Step 3
ls -l /home/user/backup.sh


Why: Verify change.

Step 4
./backup.sh