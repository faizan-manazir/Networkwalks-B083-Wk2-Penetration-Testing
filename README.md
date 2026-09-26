# Networkwalks B082 — Week 2 Penetration Testing

![Cybersecurity](https://img.shields.io/badge/Focus-Penetration%20Testing-red)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-blue)
![Program](https://img.shields.io/badge/Program-Networkwalks%20B082-black)
![Week](https://img.shields.io/badge/Week-02-success)

## Overview

This repository contains the practical work completed during **Week 2** of the Networkwalks Cybersecurity & Ethical Hacking Program.

The week focused on:

- Footprinting and passive reconnaissance
- Google Hacking Database (GHDB)
- Maltego reconnaissance
- theHarvester information gathering
- Zenmap/Nmap network discovery
- Evidence collection and professional reporting

> **Authorization & scope:** The activities documented here were performed within the assigned educational scope and against authorized targets/local infrastructure. Network scanning in PM5 was performed on my own local network.

---

## Project Modules

| Module | Activity | Main Tools |
|---|---|---|
| PM1 | Footprinting | WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon |
| PM2 | Footprinting with GHDB | Google / GHDB |
| PM3 | Maltego | Maltego |
| PM4 | Passive reconnaissance | theHarvester |
| PM5 | Network discovery | Zenmap / Nmap |

---

## Repository Structure

```text
Networkwalks-B082-Week2-Penetration-Testing/
│
├── PM1-Footprinting/
│   ├── Task1-WHOIS/
│   ├── Task2-WhatWeb/
│   ├── Task3-NSLookup/
│   ├── Task4-Curl/
│   ├── Task5-Wafw00f/
│   └── Task6-DNSRecon/
│
├── PM2-GHDB/
│   ├── GHDB.jpg
│   └── W2-PM2 - Week2 - Project Module2 - Footp with GHDB v1 - TABLES.docx
│
├── PM3-Maltego/
│   ├── Maltego_Domain.jpg
│   ├── Maltego_Result.jpg
│   └── Maltego_Setup.jpg
│
├── PM4-theHarvester/
│   ├── PM4-Task1-Baidu.txt
│   ├── PM4-Task2-All-Sources.txt
│   └── screenshots
│
├── PM5-Zenmap/
│   ├── Local_mac.jpg
│   ├── Topology.jpg
│   └── Zenmap_Live_Host.jpg
│
├── Report/
│   ├── W2-PM-FINAL_Faizan_Manazir_Report.docx
│   └── W2-PM-FINAL_Faizan_Manazir_Report.pdf
│
└── screenshots/
    └── Supporting evidence screenshots
```

---

## PM1 — Footprinting

### Target

`networkwalks.com`

### Tools

#### 1. WHOIS
Collected public domain-registration information, including registrar, creation/update/expiry dates, status and name servers.

**Recorded name servers:**
- `NS6135.HOSTGATOR.COM`
- `NS6136.HOSTGATOR.COM`

#### 2. WhatWeb
Fingerprinting identified publicly observable technologies including:

- Apache
- WordPress 7.1.2
- WordPress Download Manager 3.3.58
- Bootstrap 7.1.2
- jQuery 3.7.1
- Google Tag Manager
- HTTP cookies
- Publicly visible email: `info@networkwalks.com`

#### 3. Nslookup

The recorded DNS resolution was:

```text
networkwalks.com → 192.232.216.135
```

#### 4. Curl

HTTP response headers were collected. The response included:

- HTTP/2 200
- Apache
- WordPress REST API reference: `/wp-json/`
- WordPress page API reference
- Secure/HttpOnly cookie information

#### 5. Wafw00f

The recorded result identified:

```text
ModSecurity (SpiderLabs)
```

as the detected WAF.

#### 6. DNSRecon

The raw output and screenshot collected during the exercise are included in:

```text
PM1-Footprinting/Task6-DNSRecon/
```

---

## PM2 — Google Hacking Database

The GHDB exercise demonstrated search-engine reconnaissance using specialized Google search operators.

The collected evidence includes:

- GHDB search results
- Security-camera-related indexed results
- Mathematics directory listings
- Completed GHDB worksheet

Screenshots and the worksheet are stored under:

```text
PM2-GHDB/
```

Sensitive/actionable access information is not intentionally reproduced in this README.

---

## PM3 — Maltego

A Maltego Domain entity was created for:

```text
networkwalks.com
```

The following transform was executed:

```text
[Utilities] To Emails @domain [Search Engine]
```

The captured execution recorded:

- Entities processed: 1
- Transform: completed
- Unified credits consumed: 10
- Remaining credits at the time: 190

The Maltego screenshots are available under:

```text
PM3-Maltego/
```

---

## PM4 — theHarvester

### Task 1 — Baidu

Target:

```text
microsoft.com
```

The recorded command was:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

The raw output recorded:

- 0 IPs
- 0 emails
- 0 people
- 3 hosts

Recorded hosts:

```text
c.urs.microsoft.com
hxd.research.microsoft.com
officecdn.microsoft.com
```

### Task 2 — All Sources

The all-source reconnaissance output was saved separately because the terminal output was substantially larger.

Raw output:

```text
PM4-theHarvester/PM4-Task2-All-Sources.txt
```

The output contains source-processing information and collected host statistics. It should be treated as reconnaissance evidence rather than as proof of a vulnerability.

---

## PM5 — Zenmap / Nmap

The network discovery exercise was performed on my own local network.

### Local interface

Recorded Kali interface:

```text
eth0
IPv4: 10.0.0.3/24
MAC: 08:00:27:5A:87:BC
```

### Scan

Zenmap performed:

```bash
nmap -sn 10.0.0.0/24
```

The scan covered 256 addresses and identified three live hosts:

| IP Address | MAC Address | Status |
|---|---|---|
| 10.0.0.1 | 52:54:00:12:35:00 | Up |
| 10.0.0.2 | 08:00:27:53:38:90 | Up |
| 10.0.0.3 | 08:00:27:5A:87:BC | Up — Kali host |

The Zenmap topology and live-host evidence are stored under:

```text
PM5-Zenmap/
```

---

## Evidence

Evidence is retained in both module-specific directories and the consolidated `screenshots/` directory.

The repository includes:

- Terminal raw outputs
- Tool screenshots
- Maltego screenshots
- GHDB evidence
- theHarvester evidence
- Zenmap live-host and topology evidence
- Final DOCX report
- Final PDF report

---

## Final Report

The professional Week 2 report is available in:

```text
Report/
```

Files:

- `W2-PM-FINAL_Faizan_Manazir_Report.docx`
- `W2-PM-FINAL_Faizan_Manazir_Report.pdf`

The report provides the methodology, observations, risk analysis, recommendations, conclusion and evidence register.

---

## Key Learning Outcomes

Through these activities, I practiced:

- Passive reconnaissance
- Domain footprinting
- DNS enumeration
- Web technology fingerprinting
- HTTP header analysis
- WAF identification
- Search-engine intelligence gathering
- Graph-based reconnaissance with Maltego
- Public-source information gathering with theHarvester
- Local network host discovery
- MAC/IP identification
- Network topology visualization
- Professional cybersecurity documentation

---

## Disclaimer

This repository is provided for **educational and authorized cybersecurity training purposes**.

All reconnaissance and scanning activities should be performed only against systems, domains and networks for which appropriate authorization has been obtained.

The presence of an exposed technology, hostname, IP address, indexed page or other reconnaissance artifact does **not by itself establish a security vulnerability**. Further authorized validation would be required.

---

## Author

**Faizan Manazir**

Cybersecurity Professional — Networkwalks B083

LinkedIn: [https://www.linkedin.com/in/faizan-manazir-38046527/](https://www.linkedin.com/in/faizan-manazir-38046527a/)
