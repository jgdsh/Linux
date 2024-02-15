# Linux Commands

#### Introduction

This document is my notes of learning Linux (ubuntu) commands and usage scenarios.

#### Commands

One way to locate programs is to employ the `which` utility. For example, to find out exactly where the `diff `program resides on the filesystem

```
$ which diff
```

If which does not find the program, `whereis` is a good alternative because it looks for packages in a broader range of system directories:

```
$ whereis diff
```

`pwd` prints current working directory

```
 pwd 
```

#### Filesystem Hierarchy Standard

`/` - “Root” of the file system.  
`/bin` - Binary files and system programs.  
`/boot` - Boot loader and kernel  
`/dev` - Device files  
`/etc` - Configuration files  
`/home` - User home directories  
`/lib` - library files  
`/media` - Temporarily mounted storage  
`/opt` - Optional (installed) software  
`/root` - Root users home folder (do not confuse with root file system)  
`/run` - Information about running process  
`/srv` - Files being served by services like NFS  
`/sys` - Information about system hardware  
`/tmp` - Temporary data storage  
`/usr` - Another location for software

1\. Command shows all files in / folder listed vertically instead of horizontally

```
 ls -l / 
```

2\. Command shows all files/directories recursively (lists all files and folders inside the folder)

```
 ls -lR 
```

**Shortcut Characters**

<div class="level4" id="bkmrk-character-meaning-.-"><div class="table sectionedit2"><table class="inline"><thead><tr class="row0"><th class="col0 centeralign">Character</th><th class="col1">Meaning</th></tr></thead><tbody><tr class="row1"><td class="col0 centeralign">.</td><td class="col1">Current directory</td></tr><tr class="row2"><td class="col0 centeralign">..</td><td class="col1">Parent directory</td></tr><tr class="row3"><td class="col0 centeralign">~</td><td class="col1">User's home folder</td></tr></tbody></table>

</div></div>3\. `stat` command tells what kind of file, size etc

```
 stat opt 
```

```bash
jag@vmwubuntusrv:/$ stat opt
  File: opt
  Size: 4096            Blocks: 8          IO Block: 4096   directory
Device: 8,2     Inode: 393217      Links: 2
Access: (0755/drwxr-xr-x)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2024-01-20 18:54:17.659768231 +0000
Modify: 2023-10-11 00:36:31.000000000 +0000
Change: 2024-01-01 21:32:55.089940941 +0000
 Birth: 2024-01-01 21:32:55.021941048 +0000
```

**Text files**

Text editors like `nano` and `vim`

**Working with files and directories**

4\. `touch` command is used to create a file

```
 touch myfile 
```

```bash
jag@vmwubuntusrv:~$ touch myfile
jag@vmwubuntusrv:~$ ls
myfile
```

5\. Creating multiple files

```bash
jag@vmwubuntusrv:~$ touch myfile2 myfile3 myfile4
jag@vmwubuntusrv:~$ ls
myfile  myfile2  myfile3  myfile4
```

6\. To list all files with permissions

```bash
jag@vmwubuntusrv:~$ ls -l
total 0
-rw-rw-r-- 1 jag jag 0 Jan 20 19:53 myfile
-rw-rw-r-- 1 jag jag 0 Jan 20 19:57 myfile2
-rw-rw-r-- 1 jag jag 0 Jan 20 19:57 myfile3
-rw-rw-r-- 1 jag jag 0 Jan 20 19:57 myfile4
```

7\. Copying file from folder to another `cp`

8\. Moving files `mv`

9\. Removing/deleting files `rm`

10\. Make directories/folder `mkdir`

11\. `uname -a` Provides information about the Linux kernel version

```bash
l183admin@SWA-APP-NBX:~$ uname -a
Linux SWA-APP-NBX 6.2.0-1019-azure #19~22.04.1-Ubuntu SMP Wed Jan 10 22:57:03 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux
```

12\. `lsb_release -a` Displays information about the Ubuntu release version, including the version number, code name, and distribution description

```bash
l183admin@SWA-APP-NBX:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.3 LTS
Release:        22.04
Codename:       jammy
```

13\. `free -m` Provides information about the system’s memory usage, including the total amount of RAM installed, the amount of RAM currently in use, and the amount of free RAM available.

```bash
l183admin@SWA-APP-NBX:~$ free -m
               total        used        free      shared  buff/cache   available
Mem:            7879        1387        5822          21         669        6216
Swap:              0           0           0
```

14\. `df -h` Displays information about the disk space usage on the system, including the total amount of disk space available, the amount of space used, and the amount of space free.

```bash
l183admin@SWA-APP-NBX:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        29G  3.1G   26G  11% /
tmpfs           3.9G   28K  3.9G   1% /dev/shm
tmpfs           1.6G  1.3M  1.6G   1% /run
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/sda15      105M  6.1M   99M   6% /boot/efi
/dev/sdb1        16G   28K   15G   1% /mnt
tmpfs           788M  4.0K  788M   1% /run/user/1000
```

15.` lspci ` Displays information about the PCI devices connected to the system, such as network adapters, sound cards, and graphics cards.

16\. `lsusb` displays information about the USB devices connected to the system, such as external hard drives, cameras, and printers.

17\. `top` Displays real-time information about the system’s CPU and memory usage, including the percentage of CPU usage for each running process, the amount of RAM in use, and the amount of free memory available.

```bash
top - 18:21:02 up 53 min,  1 user,  load average: 0.00, 0.00, 0.00
Tasks: 145 total,   1 running, 144 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.2 sy,  0.0 ni, 99.7 id,  0.2 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   7879.2 total,   5815.9 free,   1391.1 used,    672.2 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   6212.5 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    559 redis     20   0   67240  17984   8832 S   0.3   0.2   0:05.85 redis-server
    592 root      20   0    7288   2688   2560 S   0.3   0.0   0:00.01 cron
   1710 root      20   0       0      0      0 I   0.3   0.0   0:00.81 kworker/1:2-events
      1 root      20   0  102208  13032   8296 S   0.0   0.2   0:02.16 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 slub_flushwq
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 netns
      8 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_percpu_wq
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     12 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     13 root      20   0       0      0      0 S   0.0   0.0   0:00.13 ksoftirqd/0
     14 root      20   0       0      0      0 I   0.0   0.0   0:01.29 rcu_sched
     15 root      rt   0       0      0      0 S   0.0   0.0   0:00.01 migration/0
     17 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     18 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     19 root      rt   0       0      0      0 S   0.0   0.0   0:00.47 migration/1
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.10 ksoftirqd/1
     22 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0H-events_highpri
```

18\. `htop` Provides the same information as the top command but with a more user-friendly interface. It allows for more straightforward navigation and sorting of processes and also includes color-coded displays for easier readability

[![image.png](https://wiki.mjagadeesh.com/uploads/images/gallery/2024-01/scaled-1680-/gYnYBNMvRhHSA0N2-image.png)](https://wiki.mjagadeesh.com/uploads/images/gallery/2024-01/gYnYBNMvRhHSA0N2-image.png)

19\.
