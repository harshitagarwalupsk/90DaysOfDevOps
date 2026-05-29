# Day 09 Challenge
## Users & Groups Created
- Users: tokyo, berlin, professor, nairobi
  
- Groups: developers, admins, project-team

## Group Assignments
developers:x:1004:tokyo,berlin

admins:x:1005:professor,berlin

project-team:x:1007:nairobi,tokyo

## Directories Created
root@ip-172-31-11-66:/opt# ll

total 16

drwxr-xr-x  4 root root         4096 May 29 18:25 ./

drwxr-xr-x 19 root root         4096 May 29 16:20 ../

drwxrwxr-x  2 root developers   4096 May 29 18:21 dev-project/

drwxrwxr-x  2 root project-team 4096 May 29 18:30 team-workspace/

## Commands Used
root@ip-172-31-11-66:/home# useradd -m tokyo
root@ip-172-31-11-66:/home# useradd -m berlin
root@ip-172-31-11-66:/home# useradd -m professor
root@ip-172-31-11-66:/home# passwd tokyo
New password:
Retype new password:
passwd: password updated successfully
root@ip-172-31-11-66:/home# passwd berlin
New password:
Retype new password:
passwd: password updated successfully
root@ip-172-31-11-66:/home# passwd professor
New password:
Retype new password:
passwd: password updated successfully
root@ip-172-31-11-66:/home#
root@ip-172-31-11-66:/home#
root@ip-172-31-11-66:/home# ll
total 24
drwxr-xr-x  6 root      root      4096 May 29 18:04 ./
drwxr-xr-x 19 root      root      4096 May 29 16:20 ../
drwxr-x---  2 berlin    berlin    4096 May 29 18:04 berlin/
drwxr-x---  2 professor professor 4096 May 29 18:04 professor/
drwxr-x---  2 tokyo     tokyo     4096 May 29 18:04 tokyo/
drwxr-x---  4 ubuntu    ubuntu    4096 May 28 19:10 ubuntu/
root@ip-172-31-11-66:/home# usermod -aG developers tokyo
root@ip-172-31-11-66:/home# usermod -aG developers berlin
root@ip-172-31-11-66:/home# usermod -aG admins professor
root@ip-172-31-11-66:/home# usermod -aG admins berlin
root@ip-172-31-11-66:~# mkdir /opt/dev-project
root@ip-172-31-11-66:/opt# chown  root:developers /opt/dev-project
root@ip-172-31-11-66:/opt# ll
total 12
drwxr-xr-x  3 root root       4096 May 29 18:09 ./
drwxr-xr-x 19 root root       4096 May 29 16:20 ../
drwxr-xr-x  2 root developers 4096 May 29 18:09 dev-project/
root@ip-172-31-11-66:/opt# chmod 775 /opt/dev-project
root@ip-172-31-11-66:/opt# su - tokyo
$ whoami
tokyo
$ cd /opt/dev-project
$ pwd
/opt/dev-project
$ cd ..
$ ll
-sh: 5: ll: not found
$
root@ip-172-31-11-66:/opt# cd
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~# chsh -s /bin/bash tokyo
root@ip-172-31-11-66:~# chsh -s /bin/bash berlin
root@ip-172-31-11-66:~# chsh -s /bin/bash professor
root@ip-172-31-11-66:~# su - tokyo
tokyo@ip-172-31-11-66:~$ cd /opt
tokyo@ip-172-31-11-66:/opt$ ll
total 12
drwxr-xr-x  3 root root       4096 May 29 18:09 ./
drwxr-xr-x 19 root root       4096 May 29 16:20 ../
drwxr-xr-x  2 root developers 4096 May 29 18:09 dev-project/
tokyo@ip-172-31-11-66:/opt/dev-project$  touch tokyo_file.txt
tokyo@ip-172-31-11-66:/opt/dev-project$
logout
root@ip-172-31-11-66:~# su - berlin
berlin@ip-172-31-11-66:~$ cd /opt/dev-project/
berlin@ip-172-31-11-66:/opt/dev-project$ touch berlin_file.txt
berlin@ip-172-31-11-66:/opt/dev-project$
logout
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~#
root@ip-172-31-11-66:~# cd /opt/dev-project/
root@ip-172-31-11-66:/opt/dev-project# ll
total 8
drwxrwxr-x 2 root   developers 4096 May 29 18:21 ./
drwxr-xr-x 3 root   root       4096 May 29 18:09 ../
-rw-rw-r-- 1 berlin berlin        0 May 29 18:21 berlin_file.txt
-rw-rw-r-- 1 tokyo  tokyo         0 May 29 18:20 tokyo_file.txt
root@ip-172-31-11-66:/opt/dev-project# su - professor
professor@ip-172-31-11-66:~$ cd /opt/dev-project/
professor@ip-172-31-11-66:/opt/dev-project$ touch professor.txt
touch: cannot touch 'professor.txt': Permission denied
professor@ip-172-31-11-66:/opt/dev-project$
logout
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project#
root@ip-172-31-11-66:/opt/dev-project# useradd -m nairobi
root@ip-172-31-11-66:/opt/dev-project# chsh -s /bin/bash nairobi
root@ip-172-31-11-66:/opt/dev-project# cd /home
root@ip-172-31-11-66:/home# ll
total 28
drwxr-xr-x  7 root      root      4096 May 29 18:22 ./
drwxr-xr-x 19 root      root      4096 May 29 16:20 ../
drwxr-x---  2 berlin    berlin    4096 May 29 18:21 berlin/
drwxr-x---  2 nairobi   nairobi   4096 May 29 18:22 nairobi/
drwxr-x---  2 professor professor 4096 May 29 18:22 professor/
drwxr-x---  2 tokyo     tokyo     4096 May 29 18:19 tokyo/
drwxr-x---  4 ubuntu    ubuntu    4096 May 28 19:10 ubuntu/
root@ip-172-31-11-66:/home# groupadd project-team
root@ip-172-31-11-66:/home# usermod -aG project-team nairobi
root@ip-172-31-11-66:/home# usermod -aG project-team tokyo
root@ip-172-31-11-66:/home# mkdir /opt/team-workspace
root@ip-172-31-11-66:/home# chmod 775 /opt/team-workspace
root@ip-172-31-11-66:/home# su - nairobi
nairobi@ip-172-31-11-66:~$ cd /opt/team-workspace/
nairobi@ip-172-31-11-66:/opt/team-workspace$
logout
root@ip-172-31-11-66:/home# cd\
>
ubuntu@ip-172-31-11-66:~$ cd /opt/team-workspace/
ubuntu@ip-172-31-11-66:/opt/team-workspace$ cd ..
ubuntu@ip-172-31-11-66:/opt$ ll
total 16
drwxr-xr-x  4 root root       4096 May 29 18:25 ./
drwxr-xr-x 19 root root       4096 May 29 16:20 ../
drwxrwxr-x  2 root developers 4096 May 29 18:21 dev-project/
drwxrwxr-x  2 root root       4096 May 29 18:25 team-workspace/
ubuntu@ip-172-31-11-66:/opt$ chown root:project-team team-workspace/
chown: changing ownership of 'team-workspace/': Operation not permitted (os error 1)
ubuntu@ip-172-31-11-66:/opt$ chown root:project-team team-workspace/
chown: changing ownership of 'team-workspace/': Operation not permitted (os error 1)
ubuntu@ip-172-31-11-66:/opt$ chown --help
Change file owner and group

Usage: chown [OPTION]... [OWNER][:[GROUP]] FILE...
       chown [OPTION]... --reference=RFILE FILE...

Arguments:
  <OWNER>
  <FILE>...

Options:
      --help                                Print help information.
  -c, --changes                             like verbose but report only when a change is made
      --from <CURRENT_OWNER:CURRENT_GROUP>  change the owner and/or group of each file only if its
                                            current owner and/or group match those specified here.
                                            Either may be omitted, in which case a match is not required
                                            for the omitted attribute
      --preserve-root                       fail to operate recursively on '/'
      --no-preserve-root                    do not treat '/' specially (the default)
      --quiet                               suppress most error messages
  -R, --recursive                           operate on files and directories recursively
      --reference <RFILE>                   use RFILE's owner and group rather than specifying OWNER:GROUP values
  -f, --silent
  -v, --verbose                             output a diagnostic for every file processed
  -H                                        if a command line argument is a symbolic link to a directory, traverse it
  -L                                        traverse every symbolic link to a directory encountered
  -P                                        do not traverse any symbolic links (default)
      --dereference                         affect the referent of each symbolic link (this is the default), rather than the symbolic link itself
  -h, --no-dereference                      affect symbolic links instead of any referenced file (useful only on systems that can change the ownership of a
                                            symlink)
  -V, --version                             Print version
ubuntu@ip-172-31-11-66:/opt$ sudo su -
root@ip-172-31-11-66:~# cd/opt
-bash: cd/opt: No such file or directory
root@ip-172-31-11-66:~# cd /opt/
root@ip-172-31-11-66:/opt# ll
total 16
drwxr-xr-x  4 root root       4096 May 29 18:25 ./
drwxr-xr-x 19 root root       4096 May 29 16:20 ../
drwxrwxr-x  2 root developers 4096 May 29 18:21 dev-project/
drwxrwxr-x  2 root root       4096 May 29 18:25 team-workspace/
root@ip-172-31-11-66:/opt# chown root:project-team team-workspace/
root@ip-172-31-11-66:/opt#
root@ip-172-31-11-66:/opt#
root@ip-172-31-11-66:/opt# ll
total 16
drwxr-xr-x  4 root root         4096 May 29 18:25 ./
drwxr-xr-x 19 root root         4096 May 29 16:20 ../
drwxrwxr-x  2 root developers   4096 May 29 18:21 dev-project/
drwxrwxr-x  2 root project-team 4096 May 29 18:25 team-workspace/
root@ip-172-31-11-66:/opt# su -nairobi
su: invalid option -- 'n'
Try 'su --help' for more information.
root@ip-172-31-11-66:/opt# su  -nairobi
su: invalid option -- 'n'
Try 'su --help' for more information.
root@ip-172-31-11-66:/opt# su - nairobi
nairobi@ip-172-31-11-66:~$ cd /opt
nairobi@ip-172-31-11-66:/opt$ ll
total 16
drwxr-xr-x  4 root root         4096 May 29 18:25 ./
drwxr-xr-x 19 root root         4096 May 29 16:20 ../
drwxrwxr-x  2 root developers   4096 May 29 18:21 dev-project/
drwxrwxr-x  2 root project-team 4096 May 29 18:25 team-workspace/
nairobi@ip-172-31-11-66:/opt$ cd team-workspace/
nairobi@ip-172-31-11-66:/opt/team-workspace$ touch nairobi.txt
nairobi@ip-172-31-11-66:/opt/team-workspace$
logout
root@ip-172-31-11-66:/opt#


## What I Learned
Give permission by reading it clearly, wrong permission can lead permission denied.
Received the Operation not permitted (os error 1) message because only the root user can change file ownership (chown) in Linux
ubuntu@ip-172-31-11-66:/opt$ chown root:project-team team-workspace/
chown: changing ownership of 'team-workspace/': Operation not permitted (os error 1)
ubuntu@ip-172-31-11-66:/opt$ chown root:project-team team-workspace/
chown: changing ownership of 'team-workspace/': Operation not permitted (os error 1)
