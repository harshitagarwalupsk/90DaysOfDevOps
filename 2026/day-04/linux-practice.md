# Practiced:

## Process inspection using ps and pgrep

root@ip-172-31-10-246:~# ps aux | head

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.3  1.7  25236 16044 ?        Ss   15:18   0:03 /sbin/init
root           2  0.0  0.0      0     0 ?        S    15:18   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        S    15:18   0:00 [pool_workqueue_release]
root           4  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/R-rcu_gp]
root           5  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/R-sync_wq]
root           6  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/R-kvfree_rcu_reclaim]
root           7  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/R-slub_flushwq]
root           8  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/R-netns]
root          10  0.0  0.0      0     0 ?        I<   15:18   0:00 [kworker/0:0H-kblockd]


root@ip-172-31-10-246:~# pgrep sshd

1082
1181
1298


## Service inspection using systemctl

root@ip-172-31-10-246:~# systemctl status ssh

● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: enabled)
    Drop-In: /usr/lib/systemd/system/ssh.service.d
             └─ec2-instance-connect.conf
     Active: active (running) since Wed 2026-05-27 15:18:13 UTC; 21min ago
 Invocation: a79f09f67c9846999c5577b32f1a1b3a
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 1075 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 1082 (sshd)
      Tasks: 1 (limit: 627)
     Memory: 6.8M (peak: 8M)
        CPU: 76ms
     CGroup: /system.slice/ssh.service
             └─1082 "sshd: /usr/sbin/sshd -D -o AuthorizedKeysCommand /usr/share/ec2-instance-connect/eic_run_authorized_keys %u %f -o AuthorizedKeysCommand>

May 27 15:18:13 ip-172-31-10-246 systemd[1]: Starting ssh.service - OpenBSD Secure Shell server...
May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on 0.0.0.0 port 22.
May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on :: port 22.
May 27 15:18:13 ip-172-31-10-246 systemd[1]: Started ssh.service - OpenBSD Secure Shell server.
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: Accepted publickey for ubuntu from 103.108.4.70 port 63666 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2>
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
root@ip-172-31-10-246:~#


root@ip-172-31-10-246:~# systemctl list-units --type=service --state=running

  UNIT                                           LOAD   ACTIVE SUB     DESCRIPTION
  acpid.service                                  loaded active running ACPI event daemon
  chrony.service                                 loaded active running chrony, an NTP client/server
  cron.service                                   loaded active running Regular background program processing daemon
  dbus.service                                   loaded active running D-Bus System Message Bus
  getty@tty1.service                             loaded active running Getty on tty1
  irqbalance.service                             loaded active running irqbalance daemon
  ModemManager.service                           loaded active running Modem Manager
  multipathd.service                             loaded active running Device-Mapper Multipath Device Controller
  networkd-dispatcher.service                    loaded active running Dispatcher daemon for systemd-networkd
  polkit.service                                 loaded active running Authorization Manager
  rsyslog.service                                loaded active running System Logging Service
  serial-getty@ttyS0.service                     loaded active running Serial Getty on ttyS0
  snap.amazon-ssm-agent.amazon-ssm-agent.service loaded active running Service for snap application amazon-ssm-agent.amazon-ssm-agent
  snapd.service                                  loaded active running Snap Daemon
  ssh.service                                    loaded active running OpenBSD Secure Shell server
  systemd-journald.service                       loaded active running Journal Service
  systemd-logind.service                         loaded active running User Login Management
  systemd-networkd.service                       loaded active running Network Management
  systemd-resolved.service                       loaded active running Network Name Resolution
  systemd-udevd.service                          loaded active running Rule-based Manager for Device Events and Files
  udisks2.service                                loaded active running Disk Manager
  unattended-upgrades.service                    loaded active running Unattended Upgrades Shutdown
  user@1000.service                              loaded active running User Manager for UID 1000

Legend: LOAD   → Reflects whether the unit definition was properly loaded.
        ACTIVE → The high-level unit activation state, i.e. generalization of SUB.
        SUB    → The low-level unit activation state, values depend on unit type.

23 loaded units listed.


## Log inspection using journalctl

root@ip-172-31-10-246:~# journalctl -u ssh --no-pager | tail -n 5

May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on 0.0.0.0 port 22.
May 27 15:18:13 ip-172-31-10-246 sshd[1082]: Server listening on :: port 22.
May 27 15:18:13 ip-172-31-10-246 systemd[1]: Started ssh.service - OpenBSD Secure Shell server.
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: Accepted publickey for ubuntu from 103.108.4.70 port 63666 ssh2: RSA SHA256:l+ZqpA0zXUlZcLMMRq4o+DFxrr2r7zrEMFhc5JC8SG0
May 27 15:25:32 ip-172-31-10-246 sshd-session[1181]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)

## Basic Linux troubleshooting workflow

root@ip-172-31-10-246:~# tail -n 20 /var/log/syslog

2026-05-27T15:33:13.959959+00:00 ip-172-31-10-246 systemd[1]: Starting systemd-tmpfiles-clean.service - Cleanup of Temporary Directories...
2026-05-27T15:33:14.074517+00:00 ip-172-31-10-246 systemd[1]: systemd-tmpfiles-clean.service: Deactivated successfully.
2026-05-27T15:33:14.074918+00:00 ip-172-31-10-246 systemd[1]: Finished systemd-tmpfiles-clean.service - Cleanup of Temporary Directories.
2026-05-27T15:35:20.936225+00:00 ip-172-31-10-246 chronyd[736]: TLS handshake with 91.189.91.113:4460 (4.ntp.ubuntu.com) failed : Error in the certificate verification. The certificate is NOT trusted. The certificate chain uses expired certificate.
2026-05-27T15:35:21.136373+00:00 ip-172-31-10-246 chronyd[736]: TLS handshake with 185.125.190.123:4460 (2.ntp.ubuntu.com) failed : Error in the certificate verification. The certificate is NOT trusted. The certificate chain uses expired certificate.
2026-05-27T15:35:21.179849+00:00 ip-172-31-10-246 chronyd[736]: TLS handshake with 91.189.91.112:4460 (3.ntp.ubuntu.com) failed : Error in the certificate verification. The certificate is NOT trusted. The certificate chain uses expired certificate.
2026-05-27T15:35:21.360960+00:00 ip-172-31-10-246 chronyd[736]: TLS handshake with 185.125.190.122:4460 (1.ntp.ubuntu.com) failed : Error in the certificate verification. The certificate is NOT trusted. The certificate chain uses expired certificate.
2026-05-27T15:40:21.339038+00:00 ip-172-31-10-246 systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
2026-05-27T15:40:21.362988+00:00 ip-172-31-10-246 systemd[1]: sysstat-collect.service: Deactivated successfully.
2026-05-27T15:40:21.367722+00:00 ip-172-31-10-246 systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
2026-05-27T15:45:30.055595+00:00 ip-172-31-10-246 kernel: workqueue: drm_fb_helper_damage_work hogged CPU for >10000us 4 times, consider switching to WQ_UNBOUND
2026-05-27T15:45:48.977443+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: 2026-05-27 15:45:48.9768 WARN EC2RoleProvider Failed to connect to Systems Manager with instance profile role credentials. Err: retrieved credentials failed to report to ssm. Error: EC2RoleRequestError: no EC2 instance role found
2026-05-27T15:45:49.078807+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: 2026-05-27 15:45:49.0086 ERROR EC2RoleProvider Failed to connect to Systems Manager with SSM role credentials. error calling RequestManagedInstanceRoleToken: AccessDeniedException: Systems Manager's instance management role is not configured for account: 965408846259
2026-05-27T15:45:49.078960+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: #011status code: 400, request id: 8e261733-6d5f-4e2b-9aa4-6306d4a776da
2026-05-27T15:45:49.179296+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: 2026-05-27 15:45:49.0086 ERROR [CredentialRefresher] Retrieve credentials produced error: no valid credentials could be retrieved for ec2 identity. Default Host Management Err: error calling RequestManagedInstanceRoleToken: AccessDeniedException: Systems Manager's instance management role is not configured for account: 965408846259
2026-05-27T15:45:49.179457+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: #011status code: 400, request id: 8e261733-6d5f-4e2b-9aa4-6306d4a776da
2026-05-27T15:45:49.279849+00:00 ip-172-31-10-246 amazon-ssm-agent.amazon-ssm-agent[1074]: 2026-05-27 15:45:49.0086 INFO [CredentialRefresher] Sleeping for 27m34s before retrying retrieve credentials
2026-05-27T15:50:11.421881+00:00 ip-172-31-10-246 systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
2026-05-27T15:50:11.446124+00:00 ip-172-31-10-246 systemd[1]: sysstat-collect.service: Deactivated successfully.
2026-05-27T15:50:11.446296+00:00 ip-172-31-10-246 systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
root@ip-172-31-10-246:~#
