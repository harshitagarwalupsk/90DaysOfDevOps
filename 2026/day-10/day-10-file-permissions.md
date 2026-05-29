# Day 10 Challenge

## Files Created
-r--r--r--  1 root root    0 May 29 18:44 devops.txt
-rw-r-----  1 root root   79 May 29 18:45 notes.txt
drwxr-xr-x  2 root root 4096 May 29 18:52 project/
-rwxrwxrwx  1 root root   51 May 29 18:47 script.sh*


## Permission Changes
#### Before
-rw-r--r--  1 root root    0 May 29 18:44 devops.txt
-rw-r--r--  1 root root   79 May 29 18:45 notes.txt
-rw-r--r--  1 root root   51 May 29 18:47 script.sh

#### After
-r--r--r--  1 root root    0 May 29 18:44 devops.txt
-rw-r-----  1 root root   79 May 29 18:45 notes.txt
drwxr-xr-x  2 root root 4096 May 29 18:52 project/
-rwxrwxrwx  1 root root   51 May 29 18:47 script.sh*


## Commands Used
chmod, vi, echo, touch, head, tail

## What I Learned
#### Root Bypasses Permission Checks:
Standard file permissions (r, w, x) apply to regular users, but the root user (UID 0) completely bypasses these ownership and write restrictions.

#### The vi behavior: 
When you edited with vi, it might have shown a [readonly] warning at the bottom, but when you saved (:wq), root overrode the restriction and wrote "tetee" to the file anyway.

#### The echo redirection: 
The append operator (>>) succeeded without a Permission denied error because root has the inherent authority to write to any standard file on the system.
