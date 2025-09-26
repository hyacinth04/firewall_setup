# Firewall Configuration and Testing (Windows & Linux UFW)

This repository contains the documentation and evidence for the network security task focusing on firewall configuration and management across two distinct operating systems.

Project Objective
The primary goal was to successfully implement, test, and manage specific packet filtering rules:

ALLOW Secure Shell (SSH) traffic on TCP Port 22.

DENY (Block) Telnet traffic on TCP Port 23 as a temporary test of the block mechanism.

Restore the system state by removing the temporary block rule.

Technologies & Environment
Component

Role

Firewall Tool Used

Host OS

Windows 10/11

Windows Defender Firewall with Advanced Security (GUI)

Virtualization

Oracle VirtualBox

N/A

Guest OS

Ubuntu 24.04 LTS Server

UFW (Uncomplicated Firewall) (CLI)

Verification

telnet utility

sudo ufw status verbose

Key Steps & Commands Demonstrated
The project involved documenting both GUI and CLI steps to manage firewall policies.

Windows Firewall (GUI)
Created a specific Outbound Rule to block TCP Port 23.

Verified the policy by attempting a connection using telnet 127.0.0.1 23 from the Command Prompt, confirming the firewall enforced the block.

Created a persistent Inbound Rule to allow TCP Port 22.

Linux UFW (CLI)
The following commands were executed sequentially on the Ubuntu Server VM:

Step

Command

Purpose

1.

sudo ufw enable

Activates the UFW service.

2.

sudo ufw deny 23/tcp

Implements the temporary block rule.

3.

sudo ufw allow 22/tcp

Implements the persistent allow rule.

4.

sudo ufw status numbered

Verifies the rules and retrieves their assigned numbers.

5.

sudo ufw delete [NUMBER]

Cleans up the environment by removing the temporary Port 23 block rule(s).

6.

sudo ufw status verbose

Final verification, confirming only Port 22 is active.

Report & Evidence
All detailed steps, command outputs, a summary of firewall operation, and required verification screenshots are contained in the main submission document: Firewall_Report.md.
