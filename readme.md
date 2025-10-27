# 🔥 Firewall Configuration and Management using UFW (Linux)

## 📘 Project Overview
This project demonstrates how to configure and manage a basic firewall on a Linux system using **UFW (Uncomplicated Firewall)**.  
The goal is to understand how firewall rules filter inbound and outbound network traffic, allowing or blocking connections to improve system security.

---

## 🎯 Objectives
- Install and enable UFW on Linux  
- View and interpret existing firewall rules  
- Add rules to block and allow specific ports  
- Test firewall functionality using Telnet and SSH  
- Document rule changes and explain firewall filtering behavior  

---

## 🧰 Tools & Environment
| Tool | Purpose |
|------|----------|
| **UFW (Uncomplicated Firewall)** | Simplified interface for iptables |
| **Telnet** | Used to test blocked ports |
| **SSH** | Used to test allowed ports |
| **Kali Linux / Ubuntu** | Operating System |

---

## ⚙️ Setup & Configuration Steps

### Step 1: Check and Enable UFW
```bash
sudo apt install ufw -y
sudo ufw enable
sudo ufw status verbose

Step 2: View Existing Rules
sudo ufw status numbered

Step 3: Block Inbound Traffic on Port 23 (Telnet)
sudo ufw deny 23/tcp

Step 4: Test the Block Rule
telnet localhost 23
# Expected: Connection refused

Step 5: Allow SSH (Port 22)
sudo ufw allow 22/tcp

Step 6: Remove the Test Rule
sudo ufw delete deny 23/tcp

Step 7: Verify Rules
sudo ufw status numbered

🧩 How a Firewall Filters Traffic

A firewall inspects data packets and decides whether to allow or block them based on defined security rules.
It filters traffic by:

Protocol: TCP, UDP, or ICMP

Port number: e.g., 22 for SSH, 23 for Telnet

Direction: Inbound or Outbound

Source/Destination: IP address or network

Only traffic matching allowed rules passes through, while all others are blocked by default.
