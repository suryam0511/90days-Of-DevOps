Environment Basics
uname -a
cat /etc/os-release

🔹 Filesystem Sanity
mkdir -p /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo

🔹 CPU & Memory
free -h
ps -o pid,pcpu,pmem,comm -C sshd

🔹 Disk & IO
df -h
du -sh /var/log

🔹 Network
ss -tulpn | grep ssh
curl -I http://localhost

🔹 Logs
journalctl -u ssh -n 50
tail -n 50 /var/log/syslog
