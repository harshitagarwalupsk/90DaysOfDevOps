# Think of Linux like a company running inside your computer.

Kernel = CEO → controls hardware and resources

User Space = Employees → apps and commands doing work

Init/Systemd = Operations Manager → starts and manages everything after boot


Now let’s break it down step-by-step in simple DevOps language.


1. Core Components of Linux

A) Kernel (The Brain of Linux)

The kernel is the core part of Linux.

It directly talks to:

CPU
RAM
Disk
Network
Devices

Users and applications cannot directly access hardware.
Everything goes through the kernel.

Kernel Responsibilities

The kernel handles:

Process management
Memory management
File systems
Networking
Security permissions
Device drivers
Example

When you run:

ping google.com

The kernel:

Creates the process
Uses network drivers
Sends packets
Receives responses
Gives output back to terminal
Important DevOps Point

If the kernel has problems:

entire server may freeze
high CPU may occur
memory leaks happen
disk/network issues appear

That’s why logs like:

dmesg
journalctl -k

are important.

B) User Space (Where Applications Run)

Everything you normally use runs in user space.

Examples:

nginx
docker
python
mysql
bash shell

User space programs cannot directly control hardware.

They ask the kernel using system calls.

Simple Flow
User Command
   ↓
Application
   ↓
Kernel
   ↓
Hardware
Example

You type:

cat file.txt

What happens:

cat runs in user space
Requests file from kernel
Kernel reads disk
Data returned to terminal
C) Init / systemd (The Startup Manager)

When Linux boots:

BIOS/UEFI
   ↓
Bootloader (GRUB)
   ↓
Kernel
   ↓
Init System (systemd)

After kernel starts, it launches the first process:

PID 1

Usually this is:

systemd
What is systemd?

systemd is the modern init system used in most Linux distributions.

It:

Starts services
Stops services
Restarts crashed services
Handles boot process
Manages logs
Handles dependencies
Why systemd Matters in DevOps

Because almost every server service is managed by it.

Examples:

nginx
docker
ssh
mysql
kubelet
Common systemd Commands
Check service status
systemctl status nginx
Start service
sudo systemctl start nginx
Stop service
sudo systemctl stop nginx
Restart service
sudo systemctl restart nginx
Enable service at boot
sudo systemctl enable nginx
View logs
journalctl -u nginx
2. How Processes Are Created and Managed

A process = running program.

Example:

Chrome running
nginx running
python script running

All are processes.

Process Creation in Linux

Linux creates processes using:

fork()
exec()
Simple Explanation
Step 1 — fork()

A process copies itself.

Example:

bash terminal creates child process
Step 2 — exec()

Child process loads actual program.

Example:

child becomes python
or nginx
or ls
Real Example

When you run:

ls

Flow:

bash shell
   ↓ fork()
child process created
   ↓ exec()
child becomes "ls"
   ↓
output shown
Viewing Processes
Show running processes
ps aux
Real-time monitoring
top

or better:

htop
Process IDs (PID)

Every process gets unique ID.

Example:

PID 1 → systemd
PID 220 → nginx
PID 500 → docker
Parent and Child Processes

Processes create other processes.

Example:

systemd
 └── nginx
      └── worker process
Kill a Process
Graceful stop
kill PID
Force stop
kill -9 PID
Process States

Common states:

State	Meaning
Running	Currently executing
Sleeping	Waiting for something
Stopped	Paused
Zombie	Finished but not cleaned
Zombie Processes

Zombie = dead process entry still remaining.

Usually happens when:

parent process doesn’t clean child properly

Too many zombies = application bug.

3. Why This Matters for DevOps Troubleshooting

Most production issues involve:

processes
memory
CPU
services
logs
Real Troubleshooting Examples
Example 1 — Website Down

Check:

systemctl status nginx

If failed:

journalctl -u nginx
Example 2 — High CPU

Find process:

top

Kill or investigate process.

Example 3 — Server Slow

Check:

memory usage
zombie processes
disk IO
stuck services
# Important Mental Model

Think like this:

systemd manages services
services run processes
processes use kernel resources
kernel controls hardware

This single line explains most Linux troubleshooting.

Beginner Practice Tasks

Try these on your Linux machine or VM.

Task 1 — Check PID 1
ps -p 1

You’ll see systemd.

Task 2 — View Running Processes
ps aux | head
Task 3 — Monitor Live Processes
top
Task 4 — Check SSH Service
systemctl status ssh

or on Ubuntu:

systemctl status sshd
Task 5 — View Logs
journalctl -xe
Final DevOps Insight

A DevOps engineer spends huge time answering questions like:

Why did service stop?
Why is CPU high?
Why is memory full?
Why didn’t app start after reboot?
Why are containers crashing?

Understanding:

kernel
processes
systemd

gives you the foundation to solve all of them.
