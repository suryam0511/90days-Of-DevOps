# Linux Commands Cheat Sheet
Focused on: Process Management | File System | Networking Troubleshooting  
Useful for DevOps & Production Debugging

---

## Process Management

| Command | Usage |
|----------|--------|
| `ps aux` | List all running processes |
| `top` | Real-time process monitoring |
| `htop` | Interactive process viewer (if installed) |
| `pidof <process>` | Get PID of a running process |
| `kill <PID>` | Terminate process by PID |
| `kill -9 <PID>` | Force kill a process |
| `pkill <name>` | Kill process by name |
| `nice -n 10 <cmd>` | Run command with adjusted priority |
| `renice -n 5 -p <PID>` | Change priority of running process |
| `uptime` | Show system load & uptime |

---

## File System & Logs

| Command | Usage |
|----------|--------|
| `ls -lah` | List files with size & permissions |
| `cd <dir>` | Change directory |
| `pwd` | Show current directory |
| `du -sh *` | Show directory sizes |
| `df -h` | Check disk space usage |
| `find /path -name "file"` | Search for file |
| `grep "text" file` | Search inside file |
| `tail -f logfile` | Live log monitoring |
| `head -n 20 file` | Show first 20 lines |
| `chmod 755 file` | Change file permissions |
| `chown user:group file` | Change file ownership |

---

## Networking Troubleshooting

| Command | Usage |
|----------|--------|
| `ip addr` | Show IP address info |
| `ping <host>` | Check network connectivity |
| `curl -I <url>` | Check HTTP response headers |
| `dig <domain>` | DNS lookup |
| `netstat -tulnp` | Show open ports & services |
| `ss -tulnp` | Modern replacement for netstat |
| `traceroute <host>` | Trace route to host |
| `nc -zv <host> <port>` | Test port connectivity |

---

## Bonus Debugging Commands (Highly Useful)

| Command | Usage |
|----------|--------|
| `free -h` | Check memory usage |
| `vmstat 1` | Monitor CPU/memory stats |
| `lsof -i :<port>` | Check which process is using a port |
| `journalctl -xe` | View systemd logs |
| `history` | Show command history |

---

## DevOps Tip

In production troubleshooting, common flow:

1. Check service status  
2. Inspect logs  
3. Check ports  
4. Validate DNS  
5. Confirm resource usage  


