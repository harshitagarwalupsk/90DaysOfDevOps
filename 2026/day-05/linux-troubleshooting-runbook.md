### root@ip-172-31-10-246:~# uname -a
Linux ip-172-31-10-246 7.0.0-1004-aws #4-Ubuntu SMP PREEMPT Mon Apr 13 13:14:24 UTC 2026 x86_64 GNU/Linux
### root@ip-172-31-10-246:~# cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
### root@ip-172-31-10-246:~# pidof sshd
12584
### root@ip-172-31-10-246:~# ps -o pid,pcpu,pmem,comm -p 12584
    PID %CPU %MEM COMMAND
  12584  0.0  0.8 sshd
### root@ip-172-31-10-246:~# free -h
               total        used        free      shared  buff/cache   available
Mem:           908Mi       349Mi       169Mi       2.7Mi       512Mi       559Mi
Swap:             0B          0B          0B
### root@ip-172-31-10-246:~# df -kh
Filesystem       Size  Used Avail Use% Mounted on
/dev/root        6.7G  2.3G  4.4G  35% /
tmpfs            455M     0  455M   0% /dev/shm
tmpfs            182M  924K  181M   1% /run
efivarfs         128K  3.1K  120K   3% /sys/firmware/efi/efivars
tmpfs            455M  4.0K  455M   1% /tmp
none             1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
none             1.0M     0  1.0M   0% /run/credentials/systemd-resolved.service
/dev/nvme0n1p13  989M   95M  828M  11% /boot
/dev/nvme0n1p15  105M  6.3M   99M   7% /boot/efi
none             1.0M     0  1.0M   0% /run/credentials/systemd-networkd.service
none             1.0M     0  1.0M   0% /run/credentials/getty@tty1.service
none             1.0M     0  1.0M   0% /run/credentials/serial-getty@ttyS0.service
tmpfs             91M  8.0K   91M   1% /run/user/1000
### root@ip-172-31-10-246:~# du -sh /var/log
17M     /var/log
### root@ip-172-31-10-246:~# ss -tulpn | grep ssh
tcp   LISTEN 0      4096              0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=12584,fd=3),("systemd",pid=1,fd=102))
tcp   LISTEN 0      4096                 [::]:22           [::]:*    users:(("sshd",pid=12584,fd=4),("systemd",pid=1,fd=103))
### root@ip-172-31-10-246:~# curl -I localhost
curl: (7) Failed to connect to localhost port 80 after 0 ms: Could not connect to server
### root@ip-172-31-10-246:~# journalctl -u sshd -n 50 --no-pager
-- No entries --
### root@ip-172-31-10-246:~# journalctl -u ssh -n 50 --no-pager
May 27 15:18:13 ip-172-31-10-246 systemd[1]: Starting ssh.service - OpenBSD Secure Shell server...
May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on 0.0.0.0 port 22.
May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on :: port 22.
May 27 15:18:13 ip-172-31-10-246 systemd[1]: Started ssh.service - OpenBSD Secure Shell server.
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: Accepted publickey for ubuntu from 103.108.4.70 port 63666 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
May 27 16:11:51 ip-172-31-10-246 sshd-session[1656]: Connection closed by 3.139.58.65 port 52056
May 27 16:28:25 ip-172-31-10-246 sshd-session[1712]: Unable to negotiate with 205.210.31.170 port 62866: no matching key exchange method found. Their offer: diffie-hellman-group-exchange-sha256,diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1,diffie-hellman-group1-sha1 [preauth]
May 27 16:32:53 ip-172-31-10-246 sshd-session[1725]: Accepted publickey for ubuntu from 103.108.4.70 port 63474 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
May 27 16:32:53 ip-172-31-10-246 sshd-session[1725]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
May 27 16:34:34 ip-172-31-10-246 systemd[1]: Stopping ssh.service - OpenBSD Secure Shell server...
May 27 16:34:34 ip-172-31-10-246 sshd[1082]: Received signal 15; terminating.
May 27 16:34:34 ip-172-31-10-246 systemd[1]: ssh.service: Deactivated successfully.
May 27 16:34:34 ip-172-31-10-246 systemd[1]: Stopped ssh.service - OpenBSD Secure Shell server.
May 27 17:12:25 ip-172-31-10-246 systemd[1]: Starting ssh.service - OpenBSD Secure Shell server...
May 27 17:12:25 ip-172-31-10-246 sshd[12584]: Server listening on 0.0.0.0 port 22.
May 27 17:12:25 ip-172-31-10-246 sshd[12584]: Server listening on :: port 22.
May 27 17:12:25 ip-172-31-10-246 systemd[1]: Started ssh.service - OpenBSD Secure Shell server.
May 27 17:12:31 ip-172-31-10-246 sshd-session[12586]: Accepted publickey for ubuntu from 103.108.4.70 port 65064 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
May 27 17:12:31 ip-172-31-10-246 sshd-session[12586]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
### root@ip-172-31-10-246:~# tail -n 50 /var/log/auth.log
2026-05-27T15:18:11.895010+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to group 'cdrom'
2026-05-27T15:18:11.895014+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to group 'sudo'
2026-05-27T15:18:11.895019+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to group 'dip'
2026-05-27T15:18:11.895023+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to group 'lxd'
2026-05-27T15:18:11.895027+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to shadow group 'adm'
2026-05-27T15:18:11.895031+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to shadow group 'cdrom'
2026-05-27T15:18:11.895035+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to shadow group 'sudo'
2026-05-27T15:18:11.895039+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to shadow group 'dip'
2026-05-27T15:18:11.895044+00:00 ip-172-31-10-246 useradd[630]: add 'ubuntu' to shadow group 'lxd'
2026-05-27T15:18:11.895051+00:00 ip-172-31-10-246 passwd[635]: password for 'ubuntu' changed by 'root'
2026-05-27T15:18:11.895458+00:00 ip-172-31-10-246 systemd-logind[667]: New seat seat0.
2026-05-27T15:18:11.895489+00:00 ip-172-31-10-246 systemd-logind[667]: Watching system buttons on /dev/input/event0 (Power Button)
2026-05-27T15:18:11.895501+00:00 ip-172-31-10-246 systemd-logind[667]: Watching system buttons on /dev/input/event1 (Sleep Button)
2026-05-27T15:18:11.895509+00:00 ip-172-31-10-246 systemd-logind[667]: Watching system buttons on /dev/input/event2 (AT Translated Set 2 keyboard)
2026-05-27T15:18:13.989221+00:00 ip-172-31-10-246 sshd[1082]: Server listening on 0.0.0.0 port 22.
2026-05-27T15:18:13.991010+00:00 ip-172-31-10-246 sshd[1082]: Server listening on :: port 22.
2026-05-27T15:25:32.285415+00:00 ip-172-31-10-246 sshd-session[1181]: Accepted publickey for ubuntu from 103.108.4.70 port 63666 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
2026-05-27T15:25:32.288613+00:00 ip-172-31-10-246 sshd-session[1181]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
2026-05-27T15:25:32.316182+00:00 ip-172-31-10-246 systemd-logind[667]: New session '1' of user 'ubuntu' with class 'user' and type 'tty'.
2026-05-27T15:25:32.346276+00:00 ip-172-31-10-246 (systemd): pam_unix(systemd-user:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
2026-05-27T15:25:32.347729+00:00 ip-172-31-10-246 systemd-logind[667]: New session '2' of user 'ubuntu' with class 'manager' and type 'unspecified'.
2026-05-27T15:26:15.942909+00:00 ip-172-31-10-246 sudo: pam_unix(sudo:session): session opened for user root(uid=0) by ubuntu(uid=1000)
2026-05-27T15:26:15.943172+00:00 ip-172-31-10-246 sudo: ubuntu : TTY=/dev/pts/0 ; PWD=/home/ubuntu ; USER=root ; COMMAND=/usr/bin/su -
2026-05-27T15:26:15.958083+00:00 ip-172-31-10-246 su[1342]: (to root) root on pts/1
2026-05-27T15:26:15.958379+00:00 ip-172-31-10-246 su[1342]: pam_unix(su-l:session): session opened for user root(uid=0) by ubuntu(uid=0)
2026-05-27T16:11:51.212541+00:00 ip-172-31-10-246 sshd-session[1656]: Connection closed by 3.139.58.65 port 52056
2026-05-27T16:17:01.723619+00:00 ip-172-31-10-246 CRON[1694]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
2026-05-27T16:17:01.733954+00:00 ip-172-31-10-246 CRON[1694]: pam_unix(cron:session): session closed for user root
2026-05-27T16:28:25.436144+00:00 ip-172-31-10-246 sshd-session[1712]: Unable to negotiate with 205.210.31.170 port 62866: no matching key exchange method found. Their offer: diffie-hellman-group-exchange-sha256,diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1,diffie-hellman-group1-sha1 [preauth]
2026-05-27T16:32:53.502309+00:00 ip-172-31-10-246 sshd-session[1725]: Accepted publickey for ubuntu from 103.108.4.70 port 63474 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
2026-05-27T16:32:53.504184+00:00 ip-172-31-10-246 sshd-session[1725]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
2026-05-27T16:32:53.509302+00:00 ip-172-31-10-246 systemd-logind[667]: New session '4' of user 'ubuntu' with class 'user' and type 'tty'.
2026-05-27T16:32:58.270190+00:00 ip-172-31-10-246 sudo: pam_unix(sudo:session): session opened for user root(uid=0) by ubuntu(uid=1000)
2026-05-27T16:32:58.275097+00:00 ip-172-31-10-246 sudo: ubuntu : TTY=/dev/pts/2 ; PWD=/home/ubuntu ; USER=root ; COMMAND=/usr/bin/su -
2026-05-27T16:32:58.276365+00:00 ip-172-31-10-246 su[1861]: (to root) root on pts/3
2026-05-27T16:32:58.276716+00:00 ip-172-31-10-246 su[1861]: pam_unix(su-l:session): session opened for user root(uid=0) by ubuntu(uid=0)
2026-05-27T16:34:34.460277+00:00 ip-172-31-10-246 sshd[1082]: Received signal 15; terminating.
2026-05-27T16:34:38.050622+00:00 ip-172-31-10-246 (systemd-stdio-bridge): pam_unix(login:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
2026-05-27T16:34:38.215256+00:00 ip-172-31-10-246 (sd-pam): pam_unix(login:session): session closed for user ubuntu
2026-05-27T17:12:25.558192+00:00 ip-172-31-10-246 sshd[12584]: Server listening on 0.0.0.0 port 22.
2026-05-27T17:12:25.559111+00:00 ip-172-31-10-246 sshd[12584]: Server listening on :: port 22.
2026-05-27T17:12:31.090218+00:00 ip-172-31-10-246 sshd-session[12586]: Accepted publickey for ubuntu from 103.108.4.70 port 65064 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
2026-05-27T17:12:31.092789+00:00 ip-172-31-10-246 sshd-session[12586]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
2026-05-27T17:12:31.107019+00:00 ip-172-31-10-246 systemd-logind[667]: New session '6' of user 'ubuntu' with class 'user' and type 'tty'.
2026-05-27T17:12:38.933582+00:00 ip-172-31-10-246 sudo: pam_unix(sudo:session): session opened for user root(uid=0) by ubuntu(uid=1000)
2026-05-27T17:12:38.939694+00:00 ip-172-31-10-246 sudo: ubuntu : TTY=/dev/pts/4 ; PWD=/home/ubuntu ; USER=root ; COMMAND=/usr/bin/su -
2026-05-27T17:12:38.941434+00:00 ip-172-31-10-246 su[12681]: (to root) root on pts/5
2026-05-27T17:12:38.941799+00:00 ip-172-31-10-246 su[12681]: pam_unix(su-l:session): session opened for user root(uid=0) by ubuntu(uid=0)
2026-05-27T17:17:01.834464+00:00 ip-172-31-10-246 CRON[12741]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
2026-05-27T17:17:01.849076+00:00 ip-172-31-10-246 CRON[12741]: pam_unix(cron:session): session closed for user root
