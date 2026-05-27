### root@ip-172-31-10-246:~# cat /etc/os-release > notes.txt
### root@ip-172-31-10-246:~# uname -r >> notes.txt
### root@ip-172-31-10-246:~# cat notes.txt
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
7.0.0-1004-aws
### root@ip-172-31-10-246:~# head -n 2 notes.txt
PRETTY_NAME="Ubuntu 26.04 LTS"
NAME="Ubuntu"
### root@ip-172-31-10-246:~# tail -n 2 notes.txt
LOGO=ubuntu-logo
7.0.0-1004-aws
