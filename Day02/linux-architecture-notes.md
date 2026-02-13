# Linux Architecture, Processes, and systemd

## Core Components
- **Kernel**: The core of Linux, manages hardware, memory, CPU scheduling, and system calls.  
- **User Space**: Where applications and utilities run, interacting with the kernel via APIs.  
- **Init/systemd**: The first process started by the kernel; systemd manages services, dependencies, and boot sequence.

## Process Lifecycle
- Processes are created via `fork()` and `exec()` system calls.  
- Each process has a unique PID and is managed by the scheduler.  
- Parent processes monitor children; exit status is passed back to the parent.  
- Signals control processes (e.g., `SIGKILL`, `SIGSTOP`).  
- Resources (CPU, memory, I/O) are allocated dynamically.  
- Processes can spawn threads for parallel execution.

## How do I check the process states

ps aux: Lists all processes with their states. Look at STAT column

## Process States
- **Running (R)**: Actively executing or ready in the run queue.  
- **Sleeping (S)**: Waiting for an event or resource, interruptible by signals.  
- **Uninterruptible Sleep (D)**: Waiting for critical I/O, cannot be interrupted.  
- **Stopped (T)**: Halted by signals or debugging tools.  
- **Zombie (Z)**: Finished execution but parent hasn’t collected exit status.  
- **Traced**: Being debugged or monitored.

## Role of systemd
- Initializes the system after boot, replacing older init systems.  
- Manages services with unit files (`.service`, `.target`).  
- Handles dependencies and parallel startup for faster boot.  
- Provides logging via `journalctl`.  
- Offers commands like `systemctl start/stop/status`.  
- Central to modern Linux troubleshooting and automation.

## Daily Commands
- `ps aux` → list processes with states.  
- `top` / `htop` → monitor CPU/memory usage in real time.  
- `systemctl status <service>` → check service health.  
- `journalctl -xe` → view logs for debugging.  
- `kill -9 <PID>` → terminate misbehaving processes.


