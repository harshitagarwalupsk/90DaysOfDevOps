# 1. Process Management

Command	Usage

ps aux	  Show all running processes

top	      Live view of CPU and memory usage

htop	Interactive process viewer (better top)

pgrep nginx	Find process ID by name

pidof docker	Get PID of a running program

kill PID	Stop a process by PID

kill -9 PID	Force kill a stuck process

pkill nginx	Kill process by name

jobs	Show background jobs in current shell

bg	Resume a stopped job in background

fg	Bring background job to foreground

nohup command &	Run command even after logout

nice -n 10 command	Start process with lower priority

renice 5 PID	Change priority of running process

systemctl status nginx	Check service status

systemctl restart nginx	Restart a service

journalctl -u nginx	View logs for a service

journalctl -xe	Inspect recent system errors


# 2. File System Commands

Command	Usage

pwd	Show current directory

ls -lah	List files with permissions and sizes

cd /path	Change directory

mkdir test	Create directory

rm -rf folder	Remove directory recursively

cp file1 file2	Copy files

mv old new	Move or rename files

touch file.txt	Create empty file

cat file.txt	Display file contents

less logfile.log	Read large files page by page

tail -f app.log	Watch logs live

head -20 file	Show first 20 lines

grep "error" app.log	Search text in files

find / -name nginx.conf	Find files by name

du -sh folder	Show folder size

df -h	Check disk usage

chmod +x script.sh	Make file executable

chown user:user file	Change file ownership

tar -czvf backup.tar.gz folder/	Compress files

unzip file.zip	Extract zip archive


# 3. Networking Troubleshooting

Command	Usage

ping google.com	Check network connectivity

ip addr	Show IP addresses

ip route	Show routing table

ss -tulnp	Show listening ports and connections

netstat -tulnp	View network ports (older systems)

curl http://example.com	Test HTTP response

curl -I https://site.com	Fetch only HTTP headers

wget URL	Download files from internet

dig google.com	DNS lookup

nslookup google.com	Query DNS server

traceroute google.com	Trace network path

hostname -I	Show local IP

nc -zv host 80	Test if port is open

telnet host 443	Check remote connectivity

tcpdump -i eth0	Capture network packets

## Quick Production Workflow

### Check if service is running
systemctl status nginx

### Watch logs in real time
tail -f /var/log/nginx/error.log

### Check CPU and memory spikes
top

### Verify open ports
ss -tulnp

### Test application response
curl http://localhost:8080

### Confirm DNS/network connectivity
ping google.com
dig google.com
