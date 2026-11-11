# Week-2-Cybersecurity-Footprinting-and-Network-Scanning
Week 2 Cybersecurity Internship – Practical work on Footprinting, Reconnaissance using six Kali Linux tools, and Network Scanning with Nmap and Zenmap.
# 🛡️ Cybersecurity Internship – Week 2
## Footprinting, Reconnaissance & Network Scanning

<p align="center">
  <b>Practical Cybersecurity Learning Portfolio</b><br>
  W2-PM1 | W2-PM5 | Networkwalks Internship
</p>

---

## 📌 Project Overview

Welcome to my Week 2 Cybersecurity Internship project!

This repository documents my practical learning activities in **Footprinting, Reconnaissance and Network Scanning**.

The purpose of these exercises was to understand how cybersecurity professionals gather information about a target domain, analyse publicly available technical information, identify network hosts and visualise network topology.

The practical work was completed using Kali Linux, Windows CMD, Nmap and Zenmap.

## 🎯 Objectives

- Understand domain footprinting and reconnaissance.
- Explore website technologies and DNS information.
- Inspect HTTP response headers.
- Practise identifying Web Application Firewall technologies.
- Discover active hosts on an authorised local network.
- Visualise network topology using Zenmap.
- Document technical findings with screenshots and observations.

## 🧰 Tools & Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Linux environment for reconnaissance |
| WHOIS | Domain registration information |
| WhatWeb | Website technology fingerprinting |
| Nslookup | DNS resolution |
| Curl -I | HTTP response header inspection |
| Wafw00f | Web Application Firewall detection |
| DNSRecon | DNS enumeration |
| Nmap | Network discovery and scanning |
| Zenmap | Graphical interface for Nmap |
| Windows CMD | Local network configuration |

## 🔍 Activity 1 – Footprinting & Reconnaissance (W2-PM1)

**Target:** `networkwalks.com`

I used six Kali Linux tools to explore different aspects of the target domain.

### 1. WHOIS

**Purpose:** Retrieve publicly available domain registration and nameserver information.

**Observation:** Collected domain registration dates, domain status information and nameserver details.

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/26d4ace0-c31b-4970-8890-f19c8f309429" />


### 2. WhatWeb

**Purpose:** Identify website technologies, CMS information and server-related details.

**Observation:** Identified WordPress-related technology and other website components.

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/c78c4f2e-c8b0-487e-afa3-37fa99d9546d" />


### 3. Nslookup

**Purpose:** Resolve a domain name into its associated IP address using DNS.

**Observation:** Successfully retrieved the domain's DNS resolution information.

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/abbd9efa-01ea-4547-9c91-010751dd3738" />


### 4. Curl -I

**Purpose:** Inspect HTTP response headers returned by the website.

**Observation:** Retrieved the HTTP response headers and observed web-server and application-related header information.

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/42bf51f4-6a34-4234-a813-418ab6670aff" />


### 5. Wafw00f

**Purpose:** Identify whether a Web Application Firewall (WAF) can be detected.

**Observation:** The tool identified ModSecurity (SpiderLabs).

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/b9f0dd71-a030-4cf4-98f0-e8ae4ce3802d" />


### 6. DNSRecon

**Purpose:** Perform DNS enumeration and examine available DNS records.

**Observation:** Collected information about nameservers, mail records, TXT records and other DNS-related entries.

**Evidence:**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/f5483e8e-c628-4dad-b018-5df3a325ad37" />


## 🌐 Activity 2 – Network Scanning with Zenmap (W2-PM5)

**Environment:** Authorised local Wi-Fi network

The second activity focused on identifying the local network configuration and discovering active hosts using Zenmap.

### Practical steps performed

1. Downloaded and installed Nmap and Zenmap from the official website.
2. Installed Npcap to enable the required network scanning functionality.
3. Used Windows CMD and `ipconfig` to identify the local IP configuration.
4. Configured the appropriate local network subnet.
5. Performed a basic Ping Scan using Zenmap.
6. Examined the scan results and opened the Topology view.
7. Saved the topology graphic as a PDF.

### Evidence 1 – Zenmap Ping Scan

<img width="1647" height="633" alt="image" src="https://github.com/user-attachments/assets/7fc271f3-8524-4b48-aa4f-a879f5966b46" />


### Evidence 2 – Zenmap Network Topology

<img width="1717" height="862" alt="image" src="https://github.com/user-attachments/assets/2650616d-eac9-4ee9-a89c-8ccfd163c4b1" />


## 📊 Key Learning Outcomes

Through these activities, I gained practical experience in:

- Domain information gathering.
- Website technology identification.
- DNS analysis and enumeration.
- HTTP response header inspection.
- Basic WAF identification.
- Network host discovery.
- Understanding IP addressing and subnets.
- Network topology visualisation.
- Cybersecurity evidence collection and documentation.

## 🔐 Ethical and Privacy Considerations

All practical activities were conducted for educational purposes and within the authorised scope.

Private network addresses, MAC addresses, cookies, DNS verification tokens and other sensitive information have been excluded from this public portfolio.

No exploitation or unauthorised access was performed as part of these exercises.

## 📚 Conclusion

Week 2 provided valuable hands-on experience in two important cybersecurity areas: footprinting and network scanning.

By using six Kali Linux tools, I learned how to gather and analyse domain, website and DNS information. Through Nmap and Zenmap, I practised local network discovery and topology visualisation.

These activities strengthened my understanding of reconnaissance, network visibility, technical documentation and responsible cybersecurity practices.

---

## 👩‍💻 Author

**Mansi Patel**  
Cybersecurity Intern | Aspiring IT Professional

🔗 **LinkedIn:** [Add your LinkedIn profile URL here]

📁 **Project:** Week 2 – Footprinting & Network Scanning  
🎓 **Program:** Networkwalks Cybersecurity Internship

---

*This repository is intended for educational and learning purposes only.*
