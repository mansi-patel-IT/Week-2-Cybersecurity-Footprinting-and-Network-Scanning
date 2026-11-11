# PENETRATION TESTING REPORT
## Footprinting, Reconnaissance & Network Scanning Phases

**W2-PM-FINAL | CYBERSECURITY INTERNSHIP | NETWORKWALKS**

| Field | Details |
|---|---|
| Pentester Name | **Mansi Patel** |
| Program / Batch | Networkwalks Cybersecurity Internship |
| Report Date | 11 November 2026 |
| Modules Completed | W2-PM1 – Multiple Kali Linux Tools; W2-PM5 – Zenmap Scanning |
| Target Domain | `networkwalks.com` |
| Network Environment | Local Wi-Fi network used for the practical |
| Phases Covered | Phase 1: Reconnaissance and Footprinting; Phase 2: Network Scanning and Discovery |

---

# 1. Liability Disclaimer

This report documents educational cybersecurity activities performed as part of an internship practical.

All testing must be conducted only against systems and networks that are owned by the tester or for which appropriate authorisation has been granted.

The activities documented here focus on information gathering, DNS enumeration, website technology identification and basic network discovery. No exploitation or unauthorised access was performed as part of these exercises.

The information is presented for educational and research purposes only. The author is responsible for ensuring that all testing remains within the permitted scope.

# 2. Introduction

This report presents the practical work completed during Week 2 of my Cybersecurity Internship at Networkwalks.

The practical work covered two main activities:

- **W2-PM1 – Footprinting and Reconnaissance:** Using six Kali Linux tools to gather and analyse domain, website, HTTP and DNS information about `networkwalks.com`.
- **W2-PM5 – Network Scanning:** Using Nmap and Zenmap on a local network to practise host discovery and network topology visualisation.

These activities helped me understand how cybersecurity professionals gather information about a target environment and identify active devices within an authorised network.

The exercises were performed using Kali Linux, Windows Command Prompt, Nmap and Zenmap.

# 3. Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Environment for reconnaissance activities |
| WHOIS | Retrieve domain registration and nameserver information |
| WhatWeb | Identify website technologies and components |
| Nslookup | Resolve domain names through DNS |
| Curl -I | Inspect HTTP response headers |
| Wafw00f | Identify detectable Web Application Firewall technologies |
| DNSRecon | Enumerate DNS records |
| Windows CMD | Identify local network configuration |
| Nmap | Perform network host discovery |
| Zenmap | Graphical interface for Nmap and topology visualisation |
| Npcap | Provide packet-capture support for Nmap on Windows |

# 4. Activities Performed

## 4.1 Footprinting and Reconnaissance – W2-PM1

**Target domain:** `networkwalks.com`

I used six Kali Linux tools to collect different categories of information about the target domain.

### 4.1.1 WHOIS

**Command used:**

```bash
whois networkwalks.com
```

**Purpose:**

WHOIS retrieves publicly available domain registration information, including registration dates, domain status and nameserver details.

**Observation:**

The command returned domain registration information, domain status entries and nameserver details. The domain creation date shown in my output was 6 November 2019.

**Security relevance:**

WHOIS information can help security professionals understand domain registration and infrastructure details during reconnaissance.

**Evidence – WHOIS output**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/44835a65-a8b6-4c13-b2fa-e48f368818bd" />


### 4.1.2 WhatWeb

**Command used:**

```bash
whatweb networkwalks.com
```

**Purpose:**

WhatWeb identifies technologies and components used by a website, such as its content management system, JavaScript libraries and web server.

**Observation:**

The scan identified WordPress-related technologies, jQuery 3.7.1, Bootstrap-related information, Apache and other website components.

**Security relevance:**

Technology fingerprinting helps identify software components that may require security review and updates. Detection results should be verified before making security conclusions.

**Evidence – WhatWeb output**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/541d9595-3388-4085-b278-c2481696b7f6" />


### 4.1.3 Nslookup

**Command used:**

```bash
nslookup networkwalks.com
```

**Purpose:**

Nslookup queries DNS to resolve a domain name into its associated IP address.

**Observation:**

The command successfully resolved `networkwalks.com` to the IPv4 address `192.232.216.135`.

**Security relevance:**

DNS resolution helps security professionals understand how a domain maps to its hosting infrastructure.

**Evidence – Nslookup output**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/db5dbe60-81e2-46d3-8800-9ecf28b09a14" />


### 4.1.4 Curl -I

**Command used:**

```bash
curl -I https://networkwalks.com
```

**Purpose:**

The `-I` option retrieves HTTP response headers without downloading the full webpage content.

**Observation:**

The server returned an HTTP/2 200 response. The headers also contained web-server and WordPress-related information, including references to the WordPress REST API.

**Security relevance:**

HTTP headers can provide useful information about server behaviour and application technologies. They should be reviewed to ensure that unnecessary technical details are not exposed.

**Evidence – Curl response headers**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/8d7a1eb7-8b92-42b3-a5ee-18d89a5d57aa" />


### 4.1.5 Wafw00f

**Command used:**

```bash
wafw00f https://networkwalks.com
```

**Purpose:**

Wafw00f checks whether a Web Application Firewall can be detected in front of a website.

**Observation:**

The tool identified ModSecurity (SpiderLabs) and completed detection using two HTTP requests.

**Security relevance:**

Identifying a WAF provides information about the website's security architecture. Detection alone does not prove that the WAF is correctly configured or that the website is secure.

**Evidence – Wafw00f output**

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/b2b6bd73-844f-4428-b74e-0e763311a1af" />


### 4.1.6 DNSRecon

**Command used:**

```bash
dnsrecon -d networkwalks.com -t std
```

**Purpose:**

DNSRecon performs DNS enumeration and examines records such as SOA, NS, A, MX, TXT and SRV.

**Observation:**

The command returned DNS-related information, including nameserver, mail-server, TXT and service records. The tool reported eight records found.

**Security relevance:**

DNS enumeration helps security professionals understand the publicly visible DNS infrastructure and identify records that may need configuration review.



## 4.2 Network Scanning with Zenmap – W2-PM5

The second practical activity focused on network discovery using Nmap and Zenmap on Windows.

### 4.2.1 Installation and Configuration

I downloaded Nmap and Zenmap from the official Nmap website and installed them on my Windows laptop.

I also installed Npcap 1.90 to provide the packet-capture functionality required for the scan.

The installer was downloaded from the official source and its SHA-256 checksum was verified against the official checksum.

### 4.2.2 Identifying Local Network Configuration

I used the Windows Command Prompt command:

```cmd
ipconfig
```

The Wi-Fi adapter displayed the following configuration:

| Network Detail | Value |
|---|---|
| Local IPv4 address | `192.168.0.104` |
| Subnet mask | `255.255.255.0` |
| Default gateway | `192.168.0.1` |
| LAN subnet | `192.168.0.0/24` |

### 4.2.3 Performing a Ping Scan

I used a basic Nmap Ping Scan to discover hosts responding on the local subnet.

**Command used:**

```cmd
nmap -sn 192.168.0.0/24
```

**Purpose:**

The `-sn` option performs host discovery without conducting a port scan.

**Observation:**

The latest confirmed Nmap text output showed two live hosts:

- `192.168.0.1`
- `192.168.0.104`

The scan reported 256 IP addresses scanned and two hosts up.

**Security relevance:**

Host discovery helps network administrators understand which devices respond on a network. Unexpected devices should be investigated by an authorised network administrator.

**Evidence – Zenmap Ping Scan**

<img width="1647" height="633" alt="image" src="https://github.com/user-attachments/assets/4764f2ec-beb6-448f-a93f-fec7371cd507" />


### 4.2.4 MAC Address Information

The scan output identified the following MAC address:

| IP address | MAC address | Identification |
|---|---|---|
| `192.168.0.1` | `24:2F:D0:6E:A0:36` | TP-Link Systems |
| `192.168.0.104` | To be verified | Local laptop |

The MAC address of the local laptop can be verified using the Windows `ipconfig /all` command.

### 4.2.5 Network Topology Visualisation

After performing the scan, I opened the Topology section in Zenmap and examined the network visualisation.

The topology evidence displayed the router and local network-related nodes. I also saved the topology graphic as a PDF.

**Evidence – Zenmap Topology**

<img width="1717" height="862" alt="image" src="https://github.com/user-attachments/assets/24a12c2e-fb1c-4997-bd58-fbe34263147b" />


**Note:** The uploaded topology PDF also displayed `192.168.0.103` and `localhost`. Since the latest confirmed Nmap text output reported two live hosts, the additional topology node must be checked before treating it as a third confirmed live device. `localhost` is not an additional physical device.

# 5. Risk Analysis and Impact

The following table summarises observations from the practical exercises. These are potential information-exposure concerns, not confirmed vulnerabilities.

| No. | Finding | Evidence / Observation | Potential Impact | Indicative Risk |
|---|---|---|---|---|
| 1 | Website technology information visible | WhatWeb identified WordPress-related components | May assist technology fingerprinting | Low |
| 2 | Domain IP resolution available | Nslookup resolved the domain | Helps identify hosting infrastructure | Low |
| 3 | HTTP response information visible | Curl returned technical response headers | May reveal application-related details | Low |
| 4 | WAF technology detectable | Wafw00f identified ModSecurity | Reveals part of the security architecture | Low |
| 5 | DNS infrastructure information available | DNSRecon returned DNS records | Helps build an infrastructure profile | Low–Medium |
| 6 | Multiple responding network hosts | Zenmap Ping Scan discovered two hosts | Helps administrators identify devices requiring verification | Informational |

**Risk assessment note:** No vulnerability exploitation or validation was performed. These findings should not be interpreted as proof that the website or local network is vulnerable.

# 6. Recommendations

Based on the activities performed, the following general security recommendations are suggested:

1. **Review exposed technology information:** Regularly review publicly visible information about website platforms and plugins.
2. **Maintain software updates:** Keep CMS platforms, plugins and server software updated.
3. **Review HTTP response headers:** Avoid unnecessarily exposing sensitive implementation details.
4. **Review DNS configurations:** Ensure that DNS records are accurate and only required information is published.
5. **Monitor WAF configuration:** Keep security controls properly configured and regularly reviewed.
6. **Perform authorised network discovery:** Periodically review active devices on networks managed by the organisation.
7. **Investigate unexpected devices:** Verify unfamiliar network devices through authorised network-administration procedures.
8. **Maintain network documentation:** Keep network diagrams and device inventories up to date.
9. **Follow ethical testing practices:** Obtain appropriate permission before conducting reconnaissance or scanning activities.

# 7. Conclusion

During Week 2 of my Cybersecurity Internship, I completed practical exercises covering footprinting, reconnaissance and network scanning.

In W2-PM1, I used six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. These exercises helped me understand domain registration information, website technology fingerprinting, DNS resolution, HTTP response headers, WAF detection and DNS enumeration.

In W2-PM5, I installed Nmap and Zenmap, configured Npcap, identified my local network configuration, performed a basic Ping Scan and generated a network topology visualisation.

The exercises strengthened my understanding of how information gathering and network discovery contribute to cybersecurity assessments.

I also learned the importance of documenting commands, observations and evidence accurately while respecting privacy and authorisation boundaries.

# 8. Evidence Collected

The practical evidence is organised in the repository's `screenshots/` folder.

| No. | Evidence | File |
|---|---|---|
| 1 | WHOIS | `01-whois.png` |
| 2 | WhatWeb | `02-whatweb.png` |
| 3 | Nslookup | `03-nslookup.png` |
| 4 | Curl -I | `04-curl-headers.png` |
| 5 | Wafw00f | `05-wafw00f.png` |
| 6 | DNSRecon | `06-dnsrecon.png` |
| 7 | Zenmap Ping Scan | `07-zenmap-ping-scan.png` |
| 8 | Zenmap Topology | `08-zenmap-topology.png` |

The original practical evidence should be retained separately for the internship submission. Public copies should be reviewed for sensitive information before publication.

# 9. Author Information

**Mansi Patel**

Cybersecurity Intern | Aspiring IT Professional

**Program:** Networkwalks Cybersecurity Internship

**LinkedIn Profile:** https://www.linkedin.com/in/mansi-patel-8a2715346/

**GitHub Repository:** https://github.com/mansi-patel-IT/Week-2-Cybersecurity-Footprinting-and-Network-Scanning/tree/main

---

*End of Report*

*Prepared for educational and internship documentation purposes.*
