---
title: How to find and kill a process running on a port in macOS
categories: [Technology, Shell]
tags: [terminal, bash]
---

To find a process on a macOS El Capitan (10.15) and newer run the below command on Terminal
```bash:
lsof -i tcp:<port_number>
```
eg: `lsof -i tcp:80`

Output of the `lsof` command
```
COMMAND   PID    USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
node    59925 abintom   23u  IPv6 0xe1a616838e9ee039      0t0  TCP *:5253 (LISTEN)
```

Kill the process using the PID from the output
```bash:
kill -9 <PID>
```
eg: `kill -9 59925`

*Note: If the above command don't work for normal user, use the command with `sudo` to run as admin.*