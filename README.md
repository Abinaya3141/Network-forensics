
# Network Forensics & Attack Traffic Analysis using Wireshark

## Objective
This project demonstrates network forensics by capturing and analyzing attack traffic on a vulnerable web application (DVWA) using Wireshark. The goal is to understand how different attacks appear in network traffic and how to detect them.

## Tools Used
- **DVWA (Damn Vulnerable Web App)** — Vulnerable web application for testing
- **Wireshark** — Packet capturing and analysis tool
- **Nmap** — Network scanning tool

## Folder Structure

Network-Forensics-Analysis/  
│  
├── captures/ ← Stores captured packet files (.pcapng)  
│   ├── normal_login.pcapng  
│   ├── sqli_attempt.pcapng  
│   └── nmap_scan.pcapng  
│  
├── screenshots/ ← Stores screenshots of Wireshark captures  
│   ├── normal_login.png  
│   ├── sqli_attempt.png  
│   └── nmap_scan.png  
│  
└── README.md ← This file

## Project Steps

### 1. Capture Normal Login
- Login credentials used:  
  - Username: `admin`  
  - Password: `password`
- Captured HTTP POST request in Wireshark showing credentials in plain text.  

**Screenshot:**  
![normal_login](https://github.com/user-attachments/assets/296f3747-3082-4862-ac67-82351b773482)


### 2. Capture SQL Injection Attempt
- Username entered: `admin' OR '1'='1 --`  
- Password left blank
- Captured SQL injection query in POST request.  

**Screenshot:**  
![sqli_attempt](https://github.com/user-attachments/assets/30cdc611-d39e-47d3-9625-d2af663267d7)


### 3. Capture Nmap Scan
- Command used: `nmap -A 127.0.0.1`  
- Captured SYN packets in Wireshark indicating scanning activity.  

**Screenshot:**  
![nmap_scan](https://github.com/user-attachments/assets/9118cd9f-7f64-40ba-a28c-6a68a82e9010)

## Findings
- Plain-text HTTP credentials → insecure login method  
- SQL injection query visible → server vulnerable to injection attacks  
- Nmap SYN packets → detectable network scanning  

---

## Mitigation Recommendations
- Use HTTPS to encrypt login credentials  
- Apply input validation and prepared statements to prevent SQL injection  
- Configure firewall rules to block unauthorized scans  
- Implement IDS/IPS to detect suspicious network activity  

---

## Advantages / Benefits
- Helps understand **real-world network attacks** in a controlled environment  
- Provides hands-on experience with **Wireshark and packet analysis**  
- Learn how to **detect malicious activities** like SQL injection and network scanning  
- Demonstrates the importance of **secure coding and network defenses**  

---


