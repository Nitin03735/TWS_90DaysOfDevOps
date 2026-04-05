##DAY 2 TASK Assignment

You will create a short note that explains:
- The core components of Linux (kernel, user space, init/systemd)
    - Kernel -> It is heart/core of linux who can communicate directly with H/w of system which form of comp prog lang like binary (0s & 1s)
    - User space -> In Linux "userspace" refers to the part of the system where normal application and user processes run as opposed to the kernal space, Where the core OS operates.
    - Init/systemd - Every time system or hardware bootup the Linux os first PID or task will be genrated/initiated PID1 as systemd.

- How processes are created and managed
    - Every time we lauch an application or run a command, System creates process for it. some are processes runs foregound and some of the running background on the system.
    - to find/manage process details we use TOP/utop or PS/ps aux commad in linux.it will show detail of running task or commad with PIDs

- What systemd does and why it matters
    - This systemd is init system and service manager in linux distribution.
    - PID-1 -> First userspace started by kernel, & everything statrted and manged by systemd.


This is the foundation for all troubleshooting you will do as a DevOps engineer.
