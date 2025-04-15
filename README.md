 # 🛡️ Network Security Assignment - 4

**By: Tanmay Saxena (Lynis) and Anirudha Desai (Nmap)**  
This repository contains the practical implementation and analysis of two essential cybersecurity tools:

- [Nmap (Network Mapper)](#-nmap-network-mapper)
- [Lynis (Linux Security Auditing Tool)](#-lynis-linux-security-auditing-tool)

Both tools were selected to complement key areas in **network** and **cloud/system security** — areas covered in our recent courses on Coursera.

---

## 🔹 Nmap (Network Mapper)

### 🧠 Why This Tool Was Chosen

Nmap is a powerful and open-source tool used for:

- Network scanning and discovery  
- Port enumeration  
- Vulnerability detection  

It is particularly useful for cloud-hosted environments and supports proactive network defense.

### ⚙️ Key Features

- Open port, service, and version detection  
- OS fingerprinting (`-O`) and script-based scans (`-sC`)  
- Host discovery for public and private networks  
- Essential for penetration testing and asset management

---

### 📥 Installation

```bash
sudo apt update
sudo apt install nmap -y
```
### 🚀 Basic Usage
```bash
# Scan localhost
nmap 127.0.0.1

# Scan a known test server
nmap scanme.nmap.org

# OS & service version detection
nmap -A 192.168.1.1

# Save results to a file
nmap -oN scan_result.txt 127.0.0.1
```
---
### 📄 Sample Use Case

#### We scanned:

- 127.0.0.1 (localhost)
- scanme.nmap.org (safe public test server)

#### Findings:

- Detected open ports like SSH (22) and HTTP (80)
- Identified service versions
- No critical vulnerabilities were found
- Useful for auditing what services are exposed

### 🧩 Issues Faced
- Some public IPs blocked scan attempts
- -A (aggressive scan) is slow; recommended for specific targets
- Ensure permissions and ethical use of the tool on target systems
---
## 🔹 Lynis (Linux Security Auditing Tool)
### 🧠 Why This Tool Was Chosen
Lynis performs in-depth security audits of Linux/Unix systems and is highly relevant for cloud systems hosted on platforms like GCP and AWS. It's lightweight, fast, and outputs a list of actionable hardening suggestions.

### ⚙️ Key Features
Full system audit with a single command
Checks:
- 🔐 Firewall rules
- 👥 User accounts & password policies
- 🗂 File permissions
- 🖧 SSH configurations

Suggests remediation steps for security hardening
---
### 📥 Installation
```bash
sudo apt update
sudo apt install lynis -y
```
### 🚀 Basic Usage
```bash
# Run audit
sudo lynis audit system

# View important suggestions
sudo cat /var/log/lynis-report.dat | grep -i "suggestion"
```
---
### 📄 Sample Use Case
We ran Lynis on a standard Ubuntu 22.04 system.
Key Findings:

- Suggested disabling SSH root login
- Recommended enabling UFW (firewall)
- Suggested secure mount options (nodev, nosuid)
- Highlighted password complexity policies

### 🧩 Issues Faced
- Requires sudo access to scan full system details
- Output is verbose; we filtered suggestions
- Some tips are advanced for beginners — we documented those separately

## 🔍 Final Thoughts
### 🧰 Tool Selection Justification
We chose these tools to explore and demonstrate:
- Nmap → for active network scanning, host discovery, and service enumeration
- Lynis → for system-level hardening of Linux servers (cloud or local)

### 📘 Key Learnings
- Nmap helped us understand network-level exposures
- Lynis revealed system misconfigurations and security posture
Combined, they provide a full-spectrum view of a system's security

## 🎓 Course Relevance
Google Cybersecurity: Connect and Protect
→ Nmap and basic network defense tools

Google Cloud Cybersecurity: Cloud Risks
→ Securing cloud-hosted Linux servers with Lynis
