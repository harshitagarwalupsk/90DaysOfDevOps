# Day 11 Challenge

## Files & Directories Created
drwx------  9 root      root       4096 May 30 18:02 ./

drwxr-xr-x 19 root      root       4096 May 30 17:25 ../

-rw-------  1 root      root       2862 May 29 19:04 .bash_history

-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc

drwx------  4 root      root       4096 May 29 16:52 .config/

-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile

drwx------  2 root      root       4096 May 28 16:51 .ssh/

-rw-------  1 root      root       2200 May 29 18:53 .viminfo

drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/

drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/

-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt

-r--r--r--  1 root      root         12 May 29 18:55 devops.txt

drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/

-rw-r-----  1 root      root         79 May 29 18:45 notes.txt

drwxr-xr-x  2 root      root       4096 May 29 18:52 project/

-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml

-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*

drwx------  3 root      root       4096 May 28 16:51 snap/

-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt

-rw-r--r-- 1 tokyo   vault-team    0 May 30 18:02 access-codes.txt

-rw-r--r-- 1 berlin  tech-team     0 May 30 18:02 blueprints.pdf

-rw-r--r-- 1 nairobi vault-team    0 May 30 18:02 escape-plan.txt


## Ownership Changes
Before:
root@ip-172-31-11-66:~# ll
total 52
drwx------  6 root  root 4096 May 30 17:54 ./
drwxr-xr-x 19 root  root 4096 May 30 17:25 ../
-rw-------  1 root  root 2862 May 29 19:04 .bash_history
-rw-r--r--  1 root  root 3106 Apr 20 08:46 .bashrc
drwx------  4 root  root 4096 May 29 16:52 .config/
-rw-r--r--  1 root  root  132 Apr 20 08:46 .profile
drwx------  2 root  root 4096 May 28 16:51 .ssh/
-rw-------  1 root  root 2200 May 29 18:53 .viminfo
-rw-r--r--  1 tokyo root    0 May 30 17:54 devops-file.txt
-r--r--r--  1 root  root   12 May 29 18:55 devops.txt
-rw-r-----  1 root  root   79 May 29 18:45 notes.txt
drwxr-xr-x  2 root  root 4096 May 29 18:52 project/
-rwxrwxrwx  1 root  root   51 May 29 18:47 script.sh*
drwx------  3 root  root 4096 May 28 16:51 snap/

After:
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt


## Commands Used
root@ip-172-31-11-66:~# touch project-config.yaml
root@ip-172-31-11-66:~# chown professor:heist-team project-config.yaml
root@ip-172-31-11-66:~# mkdir app-logs/
root@ip-172-31-11-66:~# chown berlin:heist-team app-logs/
root@ip-172-31-11-66:~# ll
total 56
drwx------  7 root      root       4096 May 30 17:58 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# mkdir -p heist-project/vault
root@ip-172-31-11-66:~# mkdir -p heist-project/plans
root@ip-172-31-11-66:~# touch heist-project/vault/gold.txt
root@ip-172-31-11-66:~# touch heist-project/plans/strategy.conf
root@ip-172-31-11-66:~# groupadd planners
root@ip-172-31-11-66:~# chown professor:planners heist-project/
root@ip-172-31-11-66:~# ls -lR heist-project/
heist-project/:
total 8
drwxr-xr-x 2 root root 4096 May 30 17:59 plans
drwxr-xr-x 2 root root 4096 May 30 17:59 vault

heist-project/plans:
total 0
-rw-r--r-- 1 root root 0 May 30 17:59 strategy.conf

heist-project/vault:
total 0
-rw-r--r-- 1 root root 0 May 30 17:59 gold.txt
root@ip-172-31-11-66:~# ll
total 60
drwx------  8 root      root       4096 May 30 17:58 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# chown -R professor:planners heist-project/
root@ip-172-31-11-66:~# ll
total 60
drwx------  8 root      root       4096 May 30 17:58 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# ls -lR heist-project/
heist-project/:
total 8
drwxr-xr-x 2 professor planners 4096 May 30 17:59 plans
drwxr-xr-x 2 professor planners 4096 May 30 17:59 vault

heist-project/plans:
total 0
-rw-r--r-- 1 professor planners 0 May 30 17:59 strategy.conf

heist-project/vault:
total 0
-rw-r--r-- 1 professor planners 0 May 30 17:59 gold.txt
root@ip-172-31-11-66:~# groupadd vault-team, tech-tea
Usage: groupadd [options] GROUP

Options:
  -f, --force                   exit successfully if the group already exists,
                                and cancel -g if the GID is already used
  -g, --gid GID                 use GID for the new group
  -h, --help                    display this help message and exit
  -K, --key KEY=VALUE           override /etc/login.defs defaults
  -o, --non-unique              allow to create groups with duplicate
                                (non-unique) GID
  -p, --password PASSWORD       use this encrypted password for the new group
  -r, --system                  create a system account
  -R, --root CHROOT_DIR         directory to chroot into
  -P, --prefix PREFIX_DIR       directory prefix
  -U, --users USERS             list of user members of this group
      --extrausers              Use the extra users database

root@ip-172-31-11-66:~# groupadd vault-team
root@ip-172-31-11-66:~# groupadd tech-team
root@ip-172-31-11-66:~# mkdir bank-heist/
root@ip-172-31-11-66:~# touch bank-heist/access-codes.txt
root@ip-172-31-11-66:~# touch bank-heist/blueprints.pdf
root@ip-172-31-11-66:~# touch bank-heist/escape-plan.txt
root@ip-172-31-11-66:~# chown tokyo:vault-team bank-heist/access-codes.txt
root@ip-172-31-11-66:~# ll
total 64
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# cd bank-heist/
root@ip-172-31-11-66:~/bank-heist# ll
\total 8
drwxr-xr-x 2 root  root       4096 May 30 18:02 ./
drwx------ 9 root  root       4096 May 30 18:02 ../
-rw-r--r-- 1 tokyo vault-team    0 May 30 18:02 access-codes.txt
-rw-r--r-- 1 root  root          0 May 30 18:02 blueprints.pdf
-rw-r--r-- 1 root  root          0 May 30 18:02 escape-plan.txt
root@ip-172-31-11-66:~/bank-heist# chown berlin:tech-team blueprints.pdf
root@ip-172-31-11-66:~/bank-heist# chown nairobi:vault-team escape-plan.txt
root@ip-172-31-11-66:~/bank-heist# ll
total 8
drwxr-xr-x 2 root    root       4096 May 30 18:02 ./
drwx------ 9 root    root       4096 May 30 18:02 ../
-rw-r--r-- 1 tokyo   vault-team    0 May 30 18:02 access-codes.txt
-rw-r--r-- 1 berlin  tech-team     0 May 30 18:02 blueprints.pdf
-rw-r--r-- 1 nairobi vault-team    0 May 30 18:02 escape-plan.txt
root@ip-172-31-11-66:~/bank-heist# cd
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~# ll
total 64
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# cd app-logs/
root@ip-172-31-11-66:~/app-logs# ll
total 8
drwxr-xr-x 2 berlin heist-team 4096 May 30 17:58 ./
drwx------ 9 root   root       4096 May 30 18:02 ../
root@ip-172-31-11-66:~/app-logs# cd
root@ip-172-31-11-66:~# ll
total 64
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# cd bank-heist/\
> ^C
root@ip-172-31-11-66:~# cd bank-heist/
root@ip-172-31-11-66:~/bank-heist# ll
total 8
drwxr-xr-x 2 root    root       4096 May 30 18:02 ./
drwx------ 9 root    root       4096 May 30 18:02 ../
-rw-r--r-- 1 tokyo   vault-team    0 May 30 18:02 access-codes.txt
-rw-r--r-- 1 berlin  tech-team     0 May 30 18:02 blueprints.pdf
-rw-r--r-- 1 nairobi vault-team    0 May 30 18:02 escape-plan.txt
root@ip-172-31-11-66:~/bank-heist# cd
root@ip-172-31-11-66:~# ll
total 64
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~# cd heist-project/
root@ip-172-31-11-66:~/heist-project# ll
total 16
drwxr-xr-x 4 professor planners 4096 May 30 17:59 ./
drwx------ 9 root      root     4096 May 30 18:02 ../
drwxr-xr-x 2 professor planners 4096 May 30 17:59 plans/
drwxr-xr-x 2 professor planners 4096 May 30 17:59 vault/
root@ip-172-31-11-66:~/heist-project# cd plans/
root@ip-172-31-11-66:~/heist-project/plans# ll
total 8
drwxr-xr-x 2 professor planners 4096 May 30 17:59 ./
drwxr-xr-x 4 professor planners 4096 May 30 17:59 ../
-rw-r--r-- 1 professor planners    0 May 30 17:59 strategy.conf
root@ip-172-31-11-66:~/heist-project/plans# cd
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~# ll
total 64
drwx------  9 root      root       4096 May 30 18:02 ./
drwxr-xr-x 19 root      root       4096 May 30 17:25 ../
-rw-------  1 root      root       2862 May 29 19:04 .bash_history
-rw-r--r--  1 root      root       3106 Apr 20 08:46 .bashrc
drwx------  4 root      root       4096 May 29 16:52 .config/
-rw-r--r--  1 root      root        132 Apr 20 08:46 .profile
drwx------  2 root      root       4096 May 28 16:51 .ssh/
-rw-------  1 root      root       2200 May 29 18:53 .viminfo
drwxr-xr-x  2 berlin    heist-team 4096 May 30 17:58 app-logs/
drwxr-xr-x  2 root      root       4096 May 30 18:02 bank-heist/
-rw-r--r--  1 tokyo     root          0 May 30 17:54 devops-file.txt
-r--r--r--  1 root      root         12 May 29 18:55 devops.txt
drwxr-xr-x  4 professor planners   4096 May 30 17:59 heist-project/
-rw-r-----  1 root      root         79 May 29 18:45 notes.txt
drwxr-xr-x  2 root      root       4096 May 29 18:52 project/
-rw-r--r--  1 professor heist-team    0 May 30 17:57 project-config.yaml
-rwxrwxrwx  1 root      root         51 May 29 18:47 script.sh*
drwx------  3 root      root       4096 May 28 16:51 snap/
-rw-r--r--  1 root      heist-team    0 May 30 17:56 team-notes.txt
root@ip-172-31-11-66:~#


## What I Learned
I learnt how to give recursive ownership to file/group
