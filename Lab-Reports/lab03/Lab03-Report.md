# Lab03 – Testing SSH Security with Nmap

## Objective
To identify an SSH service using Nmap, examine its service information, and understand SSH authentication security.

## Environment
- Operating System: Kali Linux
- Target: Local SSH lab container
- Target IP: 127.0.0.1
- Target Port: 2222

## 1. Docker Environment
Docker was already installed and running.

The running lab container was identified using:
`sudo docker ps`

The container was named `ssh_lab` and its SSH service was exposed locally on port 2222.

## 2. Nmap Scan
Command used:
`nmap -sV -p 2222 127.0.0.1`

### Observed Results
- Target host: 127.0.0.1
- Port: 2222/tcp
- State: Open
- Service: SSH
- Version: OpenSSH 9.6p1 Ubuntu 3ubuntu13.20
- Protocol: SSH 2.0

The scan confirmed that the local lab SSH service was accessible.

## 3. SSH Connection Test
Command used:
`ssh -p 2222 testuser@127.0.0.1`

The SSH server presented its host key. The key was accepted and saved in the local known_hosts file.

The subsequent authentication attempt was denied. No successful login was achieved.

## 4. Security Analysis
SSH allows users to securely connect to remote systems. Weak or reused passwords may make SSH accounts vulnerable to unauthorized access.

Security recommendations:
- Use strong and unique passwords.
- Prefer SSH key-based authentication.
- Disable password authentication where appropriate.
- Limit access to SSH using firewall rules.
- Restrict access to authorized users.
- Monitor SSH authentication logs.
- Use rate limiting or other protections against repeated login attempts.
- Keep SSH software updated.

## 5. Limitations
The service scan and single SSH connection attempt were performed against the local lab environment.

Automated password-guessing tests were not performed. No credentials were recovered, and no successful authentication was demonstrated.

## Conclusion
The exercise demonstrated how Nmap can identify an SSH service and its version information. The SSH connection test confirmed that the service was reachable, while authentication was unsuccessful. The lab highlighted the importance of secure SSH configuration and strong authentication.









