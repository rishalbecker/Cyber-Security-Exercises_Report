  GNU nano 9.0                                                                                    /home/kali/Lab-Reports/lab01/Lab01-Report.md                                                                                              









# Lab01 – Introduction to Kali Linux

## 1. Objective
The objective of this lab was to become familiar with the Kali Linux environment, its desktop interface, Linux command-line operations, and some basic cybersecurity tools.

## 2. Introduction to Kali Linux
Kali Linux is a Linux distribution designed for cybersecurity, penetration testing, digital forensics, and security-related tasks. It includes a variety of tools used for security testing, network analysis, and vulnerability assessment.

## 3. Desktop Environment Exploration
I explored the Kali Linux desktop environment and its available applications and utilities. Kali provides both graphical tools and command-line tools for cybersecurity activities.

Some tools explored or identified include:
- Nmap – Network scanning and host discovery.
- Wireshark – Network traffic analysis.
- Burp Suite – Web application security testing.
- Metasploit – Security testing framework.
- John the Ripper – Password auditing tool.

## 4. Basic Linux Commands

| Command | Description |
|---|---|
| `whoami` | Displays the current username. |
| `hostnamectl` | Displays system and operating system information. |
| `uname -a` | Displays kernel and system details. |
| `df -h` | Displays disk space usage. |
| `ip a` | Displays network interfaces and IP addresses. |
| `wget` | Downloads files from the internet. |
| `which nmap` | Locates the Nmap executable. |
| `which john` | Locates the John the Ripper executable. |
| `cd /` | Navigates to the root directory. |
| `ls -la` | Lists files, including hidden files, with details. |

### Command Results
- `whoami` returned `kali`.
- `hostnamectl` showed Kali GNU/Linux Rolling running in Oracle VirtualBox.
- `uname -a` displayed the Linux kernel and system information.
- `df -h` showed the root filesystem with approximately 79 GB total space, 19 GB used and 56 GB available.
- `ip a` displayed the network interfaces and their IP addresses.
- `wget` successfully downloaded an OWASP Cheat Sheet Series README file.
- `which nmap` returned `/usr/bin/nmap`.
- `which john` returned `/usr/sbin/john`.
- `cd /` and `ls -la` were used to explore the root filesystem.

## 5. Installation and Exploration of Linux Tools

### htop
Installed and ran htop to monitor running processes, CPU usage, memory usage, and system activity.

### traceroute
Used traceroute to examine the network route to Google.

The first hop was `10.0.2.2`. Subsequent hops did not respond to the probes, which may be due to network filtering or restrictions.

### nload
Installed and ran nload to monitor network traffic on a network interface. It displayed incoming and outgoing network traffic.

### strings
Used the strings command with `/bin/ls` to display readable text strings contained within the binary file.

### tcpdump
Used tcpdump to capture 10 network packets. The capture included network-related traffic such as IPv6 messages and DNS queries and responses.

### speedtest-cli
Attempted to install speedtest-cli using apt, but the package could not be located in the configured repositories.

### Name-That-Hash
Installed Name-That-Hash and confirmed its executable location.

### dnsenum and lbd
Checked the availability of dnsenum and lbd using the `which` command.

## 6. Nmap and Zenmap

Nmap was available on the system and its version was checked.

Zenmap, the graphical interface for Nmap, was also launched and explored.

### Localhost Scan
Executed:

`nmap 127.0.0.1`

The scan showed that the localhost was up. Most scanned ports were closed, while port 2222 was open.

### Service Detection
Executed:

`nmap -sV -p 2222 127.0.0.1`

The service detection identified port 2222 as running SSH. The detected service was OpenSSH 9.6p1 on Ubuntu Linux.

These scans were performed against my own local system.

## 7. Searchsploit

Used Searchsploit to search its local exploit database for OpenSSH-related entries.

The command used was:

`searchsploit openssh`

This displayed entries related to previously documented OpenSSH vulnerabilities and exploits. These entries are useful for security research, but their presence does not indicate that the locally detected SSH service is vulnerable.

Also explored the Searchsploit help menu.

## 8. Conclusion

In this lab, I gained practical experience with the Kali Linux operating system, basic Linux commands, system monitoring utilities, network analysis tools, and security testing applications.

I learned how to inspect system information, monitor system and network activity, explore the filesystem, perform a basic Nmap scan on localhost, identify a running service, and search the local exploit database using Searchsploit.

The lab helped me understand the basic Linux environment and the role of different tools used in cybersecurity.
