## Task
Today’s goal is to **build your Linux command confidence**.

You will create a cheat sheet of commands focused on:
- Process management
- File system
- Networking troubleshooting

This is the command toolkit you will reuse for years.


## Guidelines
Follow these rules while creating your cheat sheet:

- Include **at least 20 commands** with one‑line usage notes
- Add **3 networking commands** (`ping`, `ip addr`, `dig`, `curl`, etc.)
- Group commands by category
- Keep it concise and readable

---

## Resources
You may refer to:

- Linux `man` pages
- Your class notes
- Reliable Linux command references

Don’t copy long lists. Focus on commands you understand.

---
---
 - 1 ip addr - it will show ip4 as well as apv6 address
 - 2 netstat -tulnp -> it will show 
 - 3 traceroute -> it will showw route to the host  or print the woute packets trace to network host.
 - 4 nslookup google.com -> to check dns resolution
 - 5 dig google.com -> to debug domain issues
 - 6 nc -zv google.com 443 -> to check port 443 is reachable and debug firewall.
 - 7 wget - to validate URL or http & network
 - 8 hostname -> To get hostname of currwent system/server
 - 9 curl - to fetch web containe of given network address.
 - 10 htop - to get live data from process and extra info about PID and running process 
 - 12 kill -9 pid -> to kill perticuler task using PID
 - 13 systemctl start/stop/restart/status ngnix - service command to perform action as service level
 - 14 df -h -> to gt report file system space usage with -h (human readable)
 - 15 free --mega - > Display amount of free and used memory in the system
 - 16 du -h -> disk usage of mounted file system
 - 17 chmod - to change mode or change file permision
 - 18 ps aux -> it will show smapshot of running process and system health with CPU & memoery usage with PID,statrt end time, command performed or running.
 - 19 ss -tulnp (tcp,udp,listning ports,numric,how pid process) it will show investigate sockets
 - 20 man - to show manual fro commands
