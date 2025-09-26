# Firewall Configuration and Testing (Windows & Linux UFW)

This repository contains the documentation and evidence for the network security task focusing on firewall configuration and management across two distinct operating systems.

Project Objective
The primary goal was to successfully implement, test, and manage specific packet filtering rules:

ALLOW Secure Shell (SSH) traffic on TCP Port 22.

DENY (Block) Telnet traffic on TCP Port 23 as a temporary test of the block mechanism.

Restore the system state by removing the temporary block rule.

Technologies & Environment
Host OS: Windows 10/11 (Windows Defender Firewall with Advanced Security)

Virtualization: Oracle VirtualBox

Guest OS: Ubuntu 24.04 LTS Server (UFW - Uncomplicated Firewall)

Verification Tools: telnet utility and sudo ufw status verbose

Key Steps & Commands Demonstrated
The project involved documenting both GUI and CLI steps to manage firewall policies.

Windows Firewall (GUI)
Created a specific Outbound Rule to block TCP Port 23.

Verified the policy by attempting a connection using telnet 127.0.0.1 23 from the Command Prompt, confirming the firewall enforced the block.

Created a persistent Inbound Rule to allow TCP Port 22.

Linux UFW (CLI)
The following steps and corresponding commands were executed sequentially on the Ubuntu Server VM:

Enable UFW: sudo ufw enable

Block Port 23 (Test): sudo ufw deny 23/tcp

Allow Port 22 (Persistent): sudo ufw allow 22/tcp

Verify Rules: sudo ufw status numbered (Used to find the rule numbers for deletion)

Remove Block Rule: sudo ufw delete [NUMBER] (Executed for both IPv4 and IPv6 Port 23 block rules)

Final Verification: sudo ufw status verbose (Confirmed only Port 22 rules remain active)

Report & Evidence
All detailed steps, command outputs, a summary of firewall operation, and required verification screenshots are contained in the main submission document: Firewall_Report.md.
