# Day 04 – Linux Practice: Processes and Services

## Task
Today’s goal is to **practice Linux fundamentals with real commands**.

You will create a short practice note by actually running basic commands and capturing what you see:
- Check running processes
- Inspect one systemd service
- Capture a small troubleshooting flow

This is hands-on. Keep it simple and focused on fundamentals.

---

## Expected Output
By the end of today, you should have:

- A markdown file named:  
  `linux-practice.md`

or

- A hand written practice log (Recommended)

Your note should show what you actually ran on your system.

---

## Guidelines
Follow these rules while creating your practice note:

- Run and record output for **at least 6 commands**
- Include **2 process commands** (`ps`, `top`, `pgrep`, etc.)
 - ps
 root@ip-172-31-11-112:/var/www/html# ps
    PID TTY          TIME CMD
  16432 pts/1    00:00:00 sudo
  16433 pts/1    00:00:00 su
  16434 pts/1    00:00:00 bash
  17575 pts/1    00:00:00 ps

 - top
 top - 20:53:13 up 23:09,  2 users,  load average: 0.00, 0.00, 0.00
Tasks: 119 total,   1 running, 118 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.2 sy,  0.0 ni, 99.8 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :    911.5 total,    186.4 free,    407.5 used,    495.5 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.    503.9 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
  16367 ubuntu    20   0   15588   8520   5912 S   0.7   0.9   0:03.09 sshd
      1 root      20   0   22588  13188   8856 S   0.0   1.4   0:07.21 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.01 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_gp
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-sync_wq
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-kvfree_rcu_reclaim
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_flushwq
      8 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     11 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     13 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_percpu_wq
     14 root      20   0       0      0      0 S   0.0   0.0   0:00.16 ksoftirqd/0
     15 root      20   0       0      0      0 I   0.0   0.0   0:01.96 rcu_sched
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_exp_par_gp_kthread_worker/0
     17 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_exp_gp_kthread_worker
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.41 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.40 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.14 ksoftirqd/1
     26 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0H-events_highpri
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kdevtmpfs
     28 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-inet_frag_wq
     29 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread

- Include **2 service commands** (`systemctl status`, `systemctl list-units`, etc.)
 - 
 
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; preset: enabled)
     Active: active (running) since Mon 2026-04-06 20:17:55 UTC; 36min ago
       Docs: man:nginx(8)
    Process: 17289 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 17291 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
   Main PID: 17320 (nginx)
      Tasks: 3 (limit: 1004)
     Memory: 2.7M (peak: 5.3M)
        CPU: 34ms
     CGroup: /system.slice/nginx.service
             ├─17320 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             ├─17323 "nginx: worker process"
             └─17324 "nginx: worker process"

Apr 06 20:17:55 www.google.com systemd[1]: Starting nginx.service - A high performance web server and a reverse proxy server...
Apr 06 20:17:55 www.google.com systemd[1]: Started nginx.service - A high performance web server and a reverse proxy server.


- Include **2 log commands** (`journalctl -u <service>`, `tail -n 50`, etc.)
    Apr 06 20:17:01 www.google.com CRON[17038]: pam_unix(cron:session): session closed for user root
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading requested from client PID 17188 ('systemctl') (unit session-159.scope)...
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading...
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading finished in 256 ms.
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading requested from client PID 17238 ('systemctl') (unit session-159.scope)...
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading...
    Apr 06 20:17:55 www.google.com systemd[1]: Reloading finished in 267 ms.
    Apr 06 20:17:55 www.google.com systemd[1]: Starting nginx.service - A high performance web server and a reverse proxy server...
    Apr 06 20:17:55 www.google.com systemd[1]: Started nginx.service - A high performance web server and a reverse proxy server.
    Apr 06 20:17:58 www.google.com dbus-daemon[586]: [system] Activating via systemd: service name='org.freedesktop.PackageKit' unit='packagekit.service' requested by ':1.163' (uid=0 pid=17339 comm="/usr/bin/gdbus call --system --dest org.freedeskto" label="unconfined")
    Apr 06 20:17:58 www.google.com systemd[1]: Starting packagekit.service - PackageKit Daemon...
    Apr 06 20:17:58 www.google.com PackageKit[17343]: daemon start
    Apr 06 20:17:58 www.google.com dbus-daemon[586]: [system] Successfully activated service 'org.freedesktop.PackageKit'
    Apr 06 20:17:58 www.google.com systemd[1]: Started packagekit.service - PackageKit Daemon.
    Apr 06 20:20:14 www.google.com systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
    Apr 06 20:20:14 www.google.com systemd[1]: sysstat-collect.service: Deactivated successfully.
    Apr 06 20:20:14 www.google.com systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
    Apr 06 20:21:53 www.google.com sshd[17430]: Connection closed by authenticating user root 135.19.202.236 port 38426 [preauth]
    Apr 06 20:23:04 www.google.com PackageKit[17343]: daemon quit
    Apr 06 20:23:04 www.google.com systemd[1]: packagekit.service: Deactivated successfully.
    Apr 06 20:25:01 www.google.com CRON[17470]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
    Apr 06 20:25:01 www.google.com CRON[17471]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
    Apr 06 20:25:01 www.google.com CRON[17470]: pam_unix(cron:session): session closed for user root
    Apr 06 20:27:23 www.google.com sshd[17488]: Invalid user vpn from 135.19.202.236 port 53222
    Apr 06 20:27:32 www.google.com sshd[17488]: Connection closed by invalid user vpn 135.19.202.236 port 53222 [preauth]
    Apr 06 20:30:14 www.google.com systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
    Apr 06 20:30:14 www.google.com systemd[1]: sysstat-collect.service: Deactivated successfully.
    Apr 06 20:30:14 www.google.com systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
    Apr 06 20:33:14 www.google.com sshd[17510]: Connection closed by authenticating user root 135.19.202.236 port 44124 [preauth]
    Apr 06 20:33:28 www.google.com amazon-ssm-agent.amazon-ssm-agent[956]: 2026-04-06 20:33:28.7813 WARN EC2RoleProvider Failed to connect to Systems Manager with instance profile role credentials. Err: retrieved credentials failed to report to ssm. Error: EC2RoleRequestError: no EC2 instance role found
    Apr 06 20:33:28 www.google.com amazon-ssm-agent.amazon-ssm-agent[956]: 2026-04-06 20:33:28.8130 ERROR EC2RoleProvider Failed to connect to Systems Manager with SSM role credentials. error calling RequestManagedInstanceRoleToken: AccessDeniedException: Systems Manager's instance management role is not configured for account: 517149105777
    Apr 06 20:33:28 www.google.com amazon-ssm-agent.amazon-ssm-agent[956]:         status code: 400, request id: 41d13c04-08d9-4bae-ba4b-8e6221587e2d
    Apr 06 20:35:01 www.google.com CRON[17513]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
    Apr 06 20:35:01 www.google.com CRON[17514]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
    Apr 06 20:35:01 www.google.com CRON[17513]: pam_unix(cron:session): session closed for user root
    Apr 06 20:38:39 www.google.com sshd[17517]: Invalid user deploy from 135.19.202.236 port 35614
    Apr 06 20:38:46 www.google.com sshd[17517]: Connection closed by invalid user deploy 135.19.202.236 port 35614 [preauth]
    Apr 06 20:40:14 www.google.com systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
    Apr 06 20:40:14 www.google.com systemd[1]: sysstat-collect.service: Deactivated successfully.
    Apr 06 20:40:14 www.google.com systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
    Apr 06 20:44:33 www.google.com sshd[17550]: Connection closed by authenticating user root 135.19.202.236 port 49310 [preauth]
    Apr 06 20:45:01 www.google.com CRON[17553]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
    Apr 06 20:45:01 www.google.com CRON[17554]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
    Apr 06 20:45:01 www.google.com CRON[17553]: pam_unix(cron:session): session closed for user root
    Apr 06 20:49:02 www.google.com irqbalance[12392]: Cannot change IRQ 26 affinity: Permission denied
    Apr 06 20:49:02 www.google.com irqbalance[12392]: IRQ 26 affinity is now unmanaged
    Apr 06 20:49:49 www.google.com sshd[17563]: Connection closed by authenticating user root 135.19.202.236 port 38542 [preauth]
    Apr 06 20:50:41 www.google.com systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
    Apr 06 20:50:41 www.google.com systemd[1]: sysstat-collect.service: Deactivated successfully.
    Apr 06 20:50:41 www.google.com systemd[1]: Finished sysstat-collect.service - system activity accounting tool.

- Pick **one service on your system** (example: `ssh`, `cron`, `docker`) and inspect it
DOCKER 

    root@ip-172-31-11-112:/var/www/html# docker --version
    Docker version 28.2.2, build 28.2.2-0ubuntu1~24.04.1
    root@ip-172-31-11-112:/var/www/html# docker ps
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    root@ip-172-31-11-112:/var/www/html# systemctl status docker
    ● docker.service - Docker Application Container Engine
        Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; preset: enabled)
        Active: active (running) since Mon 2026-04-06 20:59:04 UTC; 2min 19s ago
    TriggeredBy: ● docker.socket
        Docs: https://docs.docker.com
    Main PID: 18097 (dockerd)
        Tasks: 9
        Memory: 33.7M (peak: 34.1M)
            CPU: 448ms
        CGroup: /system.slice/docker.service
                └─18097 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.185300988Z" level=info msg="Loading containers: start."
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.552809048Z" level=info msg="Loading containers: done."
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.603558422Z" level=info msg="Docker daemon" commit="28.2.2-0ubuntu1~2>
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.603704297Z" level=info msg="Initializing buildkit"
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.613979051Z" level=warning msg="CDI setup error /etc/cdi: failed to m>
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.614016833Z" level=warning msg="CDI setup error /var/run/cdi: failed >
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.634227831Z" level=info msg="Completed buildkit initialization"
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.643005502Z" level=info msg="Daemon has completed initialization"
    Apr 06 20:59:04 www.google.com dockerd[18097]: time="2026-04-06T20:59:04.643230831Z" level=info msg="API listen on /run/docker.sock"
    Apr 06 20:59:04 www.google.com systemd[1]: Started docker.service - Docker Application Container Engine.



SSH
    ssh.service - OpenBSD Secure Shell server
        Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: enabled)
        Drop-In: /usr/lib/systemd/system/ssh.service.d
                └─ec2-instance-connect.conf
        Active: active (running) since Sun 2026-04-05 21:43:58 UTC; 23h ago
    TriggeredBy: ● ssh.socket
        Docs: man:sshd(8)
                man:sshd_config(5)
    Main PID: 1014 (sshd)
        Tasks: 1 (limit: 1004)
        Memory: 6.6M (peak: 9.5M)
            CPU: 12.849s
        CGroup: /system.slice/ssh.service
                └─1014 "sshd: /usr/sbin/sshd -D -o AuthorizedKeysCommand /usr/share/ec2-instance-connect/eic_run_authorized_keys %u %f -o Author>

    Apr 06 20:16:10 www.google.com sshd[17036]: Connection closed by authenticating user root 135.19.202.236 port 41548 [preauth]
    Apr 06 20:21:53 www.google.com sshd[17430]: Connection closed by authenticating user root 135.19.202.236 port 38426 [preauth]
    Apr 06 20:27:23 www.google.com sshd[17488]: Invalid user vpn from 135.19.202.236 port 53222
    Apr 06 20:27:32 www.google.com sshd[17488]: Connection closed by invalid user vpn 135.19.202.236 port 53222 [preauth]
    Apr 06 20:33:14 www.google.com sshd[17510]: Connection closed by authenticating user root 135.19.202.236 port 44124 [preauth]
    Apr 06 20:38:39 www.google.com sshd[17517]: Invalid user deploy from 135.19.202.236 port 35614
    Apr 06 20:38:46 www.google.com sshd[17517]: Connection closed by invalid user deploy 135.19.202.236 port 35614 [preauth]
    Apr 06 20:44:33 www.google.com sshd[17550]: Connection closed by authenticating user root 135.19.202.236 port 49310 [preauth]
    Apr 06 20:49:49 www.google.com sshd[17563]: Connection closed by authenticating user root 135.19.202.236 port 38542 [preauth]
    Apr 06 20:55:48 www.google.com sshd[17579]: Connection closed by authenticating user root 135.19.202.236 port 47192 [preauth]

- Keep it **simple and actionable**


- Process checks
- Service checks
- Log checks
- Mini troubleshooting steps


## Why This Matters for DevOps
Hands‑on practice builds speed and confidence.

When issues happen in production, you won’t have time to search for basic commands.  
This day helps you build muscle memory with Linux fundamentals.