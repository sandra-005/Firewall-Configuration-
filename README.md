# Linux Firewall Configuration using UFW

## Overview
This repository demonstrates how to configure and test a firewall on a Linux system using UFW (Uncomplicated Firewall). The task includes installing UFW, allowing necessary services, blocking unwanted ports, testing firewall rules, enabling logging, and documenting the results.

## Objectives
- Install and enable UFW on a Linux system.
- Allow SSH connections to prevent remote lockout.
- Block inbound traffic on Telnet (port 23) for security.
- Test firewall rules using tools like Nmap.
- Enable firewall logging and document configuration.
- Understand firewall rule management and verification.

## Tools Required
- Linux system (Kali)
- UFW (Uncomplicated Firewall)
- Nmap or other network scanning tools
- Terminal / Shell

## Procedure
1. Open the terminal and install UFW:
   ```
   sudo apt update
   sudo apt install ufw -y
   sudo ufw enable
2. Allow SSH (port 22) to prevent lockout:
```
sudo ufw allow 22/tcp
```
3. Check current firewall rules:

```
sudo ufw status verbose
sudo ufw status numbered
```
4. Block Telnet (port 23):
```
sudo ufw deny 23/tcp
```

5. Test the rule using Nmap:
```
nmap -p 23 <target-ip>
```

6. Ensure SSH access remains allowed:
```
sudo ufw allow 22/tcp
```

7. Remove the test block rule:
```
sudo ufw delete deny 23/tcp
```
8. Enable logging and verify configuration:
```
sudo ufw logging on
sudo ufw status verbose
```
9. Document commands and outputs:
```
sudo ufw status verbose | tee ufw-status.txt
