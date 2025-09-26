# Firewall Configuration and Testing (Windows & Linux UFW)
This repository contains the documentation and evidence for Task: Setup and Use a Firewall on Windows/Linux. The project objective was to demonstrate the ability to configure, test, and manage basic network filtering rules across two different operating systems.

Project Objective
To configure and test firewall rules to selectively allow or block network traffic, specifically:

Block (DENY): Telnet traffic on TCP Port 23 (Temporary Test Rule)

Allow (ALLOW): Secure Shell (SSH) traffic on TCP Port 22 (Persistent Rule)

Theoretical Summary: How Firewalls Filter Traffic
A firewall acts as a security checkpoint, examining network packets against a defined Rule Set to determine whether traffic is allowed or blocked. Filtering is primarily based on:

IP Address: Source and Destination.

Protocol: TCP or UDP.

Port Number: The application channel (e.g., 22, 23, 80).

Traffic is processed top-down through the rules. The first rule to match the packet determines the action (ALLOW, DENY, or REJECT). If no rule matches, the firewall applies its Default Policy (typically DENY).

Tools and Environment
Component

Role

Notes

Host OS

Windows 10/11

Used for local testing and running the VM.

Virtualization

Oracle VirtualBox

Used to host the Linux Server VM.

Guest OS

Ubuntu 24.04 LTS Server

Used for command-line firewall configuration.

Firewalls

Windows Defender Firewall with Advanced Security (GUI)

UFW (Uncomplicated Firewall) on Linux (CLI)

Key Steps Performed
This project demonstrated the ability to handle both Graphical and Command-Line firewall management:

Windows Firewall (GUI)
Created an Outbound Rule using the GUI to explicitly Block TCP Port 23.

Verified the rule using the telnet 127.0.0.1 23 command, proving the firewall successfully enforced the block policy.

Linux Firewall (UFW - CLI)
Enabled the UFW service using sudo ufw enable.

Applied a block rule (sudo ufw deny 23/tcp) and an allow rule (sudo ufw allow 22/tcp).

Verified the state using sudo ufw status numbered (Step 2).

Used the sudo ufw delete [NUMBER] command to carefully remove the temporary Port 23 block rules (Step 6).

Restored the final state to only allow SSH traffic (Port 22).

Deliverables
The final report (Firewall_Report.pdf) contains the full documentation, including:

A summary of how packet filtering firewalls operate.

Screenshots documenting every required step and command.

Final verification of the clean state on both systems.
