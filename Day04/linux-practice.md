
<!-- Process commands -->

ps: process state

ubuntu@web-server:~$ ps
    PID TTY          TIME CMD
   2706 pts/0    00:00:00 bash
   2721 pts/0    00:00:00 ps

   D:\Surya\Project\90daysOfDevOps\Day04\linux-practice.md

=====================================================

top: view running system processes

ubuntu@web-server:~$ top
top - 13:29:30 up 4 min,  1 user,  load average: 0.08, 0.14, 0.07
Tasks: 106 total,   1 running, 105 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.3 sy,  0.0 ni, 89.3 id,  0.0 wa,  0.0 hi,  0.0 si, 10.4 st
MiB Mem :    957.3 total,    268.2 free,    224.1 used,    465.0 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.    570.0 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0   18772  11520   8320 S   0.0   1.2   0:01.69 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
      8 root      20   0       0      0      0 I   0.0   0.0   0:00.01 kworker/0:0-cgroup_destroy
      9 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/0:1-events
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.12 kworker/u30:0-events_unbound


=====================================================

pgrep: shares pid of running process

ubuntu@web-server:~$ pgrep 'ksmd'
29
ubuntu@web-server:~$
ubuntu@web-server:~$ pgrep 'rcu_sched'
16

=====================================================

<!-- Service commands -->

systemctl status: view log and status of specific service

ubuntu@web-server:~$ systemctl status
● web-server
    State: running
     Jobs: 0 queued
   Failed: 0 units
    Since: Fri 2026-02-13 13:24:32 UTC; 7min ago
   CGroup: /
           ├─user.slice
           │ └─user-1000.slice
           │   ├─user@1000.service
           │   │ └─init.scope


=====================================================

systemctl list-units: lists all units currently known to systemd

ubuntu@web-server:~$ systemctl list-units
  UNIT                                                                         LOAD   ACTIVE     SUB       DESCRIPTION                                                     >
  proc-sys-fs-binfmt_misc.automount                                            loaded active     running   Arbitrary Executable File Formats File System Automount Point   >
  dev-loop0.device                                                             loaded activating tentative /dev/loop0
  dev-loop1.device                                                             loaded activating tentative /dev/loop1
  dev-loop2.device                                                             loaded activating tentative /dev/loop2
  dev-loop3.device                                                             loaded activating tentative /dev/loop3
  dev-loop4.device                                                             loaded activating tentative /dev/loop4
  dev-loop5.device                                                             loaded activating tentative /dev/loop5
  dev-loop6.device                                                             loaded activating tentative /dev/loop6
  dev-loop7.device                                                             loaded activating tentative /dev/loop7
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.1-tty-ttyS1.device loaded active     plugged   /sys/devices/platform/serial8250/


=====================================================

<!-- Log command -->

journalctl -u <service>: viewing, filtering, and managing system logs managed by systemd-journald

ubuntu@web-server:~$ journalctl -u boot-efi.mount
Dec 17 11:42:21 ubuntu systemd[1]: Mounting /boot/efi...
Dec 17 11:42:21 ubuntu systemd[1]: Mounted /boot/efi.
Dec 17 15:04:47 ip-172-31-1-235 systemd[1]: Unmounting /boot/efi...
Dec 17 15:04:47 ip-172-31-1-235 systemd[1]: boot-efi.mount: Deactivated successfully.
Dec 17 15:04:47 ip-172-31-1-235 systemd[1]: Unmounted /boot/efi.
-- Boot c5d45aeedcd243eeae6e3406bd8a6766 --

=====================================================

tail -f n10

displays the last part (10 lines by default) of one or more files or piped data

=====================================================
