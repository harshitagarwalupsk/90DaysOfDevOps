# / (Root Directory)
This is the top-level directory in Linux. Everything in Linux starts from /
### I would use this when...
I need to navigate the full Linux filesystem or understand overall system structure.
### Example items you may see:
home/

etc/

# /home
Stores personal directories for normal users. Each user usually gets their own folder here
### I would use this when...
I want to access user files, scripts, downloads, or project folders.
### Example items you may see:
ubuntu/

developer/

# /root
This is the home directory of the root (admin) user. Only privileged users should access it.
### I would use this when...
I am working as the root user and need admin-level configuration or scripts.
### Example items you may see:
.bashrc

.ssh/

# /etc
Stores system-wide configuration files and service settings. Very important for DevOps and troubleshooting.
### I would use this when...
I need to modify server configuration, networking, or service settings.
### Example items you may see:
hosts

ssh/

# /var/log
Stores system and application log files. This is one of the most important directories during troubleshooting.
### I would use this when...
I need to investigate errors, failed logins, crashes, or service issues.
### Example items you may see:
syslog

auth.log

# /tmp
Stores temporary files created by users or applications. Files here may get deleted automatically after reboot.
### I would use this when...
I need a temporary place to test scripts or store short-lived files.

# /bin
Contains essential command binaries required for basic system operation.
### I would use this when...
I want to understand where basic Linux commands are stored.
### Example items you may see:
ls

cp

# /usr/bin
Contains most user-level executable programs and utilities installed on the system.
### I would use this when...
I need to locate installed tools and application binaries.
### Example items you may see:
python3

curl

# /opt
Used for optional or third-party software installations.
### I would use this when...
I install or manage third-party applications manually.
### Example items you may see:
google/

Custom application folders

## Directory	            Easy Memory
/	                    Everything starts here
/home	                User personal files
/root	                Admin user's home
/etc	                Editable configs
/var/log	            Logs for troubleshooting
/tmp	                Temporary testing area
/bin	                Basic commands
/usr/bin	            Installed programs
/opt	                Optional software



### root@ip-172-31-11-66:~# du -sh /var/log/* 2>/dev/null | sort -h | tail -5
128K    /var/log/kern.log
280K    /var/log/cloud-init.log
284K    /var/log/sysstat
388K    /var/log/syslog
17M     /var/log/journal
### root@ip-172-31-11-66:~# cat /etc/hostname
ip-172-31-11-66
### root@ip-172-31-11-66:~# ls -la ~
total 28
drwx------  4 root root 4096 May 29 06:03 .
drwxr-xr-x 19 root root 4096 May 29 16:20 ..
-rw-------  1 root root   23 May 29 06:03 .bash_history
-rw-r--r--  1 root root 3106 Apr 20 08:46 .bashrc
-rw-r--r--  1 root root  132 Apr 20 08:46 .profile
drwx------  2 root root 4096 May 28 16:51 .ssh
drwx------  3 root root 4096 May 28 16:51 snap
