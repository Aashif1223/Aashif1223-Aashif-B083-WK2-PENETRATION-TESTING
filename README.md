# Aashif Rahman --- NetworkWalks Week 2: Penetration Testing

![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-blue)
![Program](https://img.shields.io/badge/NetworkWalks-B083-green)
![Week](https://img.shields.io/badge/Week-02-orange)
![Focus](https://img.shields.io/badge/Focus-Footprinting%20%26%20Network%20Scanning-purple)

## 📌 Project Overview

This repository contains my **Week 2 practical work** from the
**NetworkWalks Cybersecurity Program --- Batch B083**.

The week focused on:

-   Footprinting and reconnaissance
-   Web technology fingerprinting
-   DNS information gathering
-   HTTP response/header inspection
-   WAF detection
-   DNS record enumeration
-   Network/service discovery with Zenmap (Nmap GUI)
-   Evidence collection and security documentation

> **Educational / Authorized Use:** All activities documented here were
> performed as part of cybersecurity training and within the assigned
> lab/authorized scope. Reconnaissance and scanning should not be
> performed against systems without permission.

------------------------------------------------------------------------

## 🛠️ Tools Used

  Tool            Purpose
  --------------- --------------------------------------------
  WHOIS           Domain registration and ownership metadata
  WhatWeb         Web technology fingerprinting
  nslookup        DNS resolution
  curl            HTTP response/header inspection
  wafw00f         WAF detection
  DNSRecon        DNS enumeration
  Zenmap / Nmap   Network and service discovery
  Kali Linux      Security testing environment

------------------------------------------------------------------------

## 🔎 Activities Performed

### 1. WHOIS --- Domain Information

**Command**

``` bash
whois networkwalks.com
```

**Observation:** Registration metadata, registrar information, name
servers, domain status and DNSSEC-related information were returned.

**Evidence:**
[`01_WHOIS_Domain_Information.png`](Evidence/01_WHOIS_Domain_Information.png)

------------------------------------------------------------------------

### 2. WhatWeb --- Web Fingerprinting

**Command**

``` bash
whatweb networkwalks.com
```

**Observation:** The supplied evidence identified technologies and
headers including Apache, WordPress, WordPress Download Manager and
jQuery.

**Evidence:**
[`02_WhatWeb_Web_Technology_Fingerprinting.png`](Evidence/02_WhatWeb_Web_Technology_Fingerprinting.png)

------------------------------------------------------------------------

### 3. nslookup --- DNS Resolution

**Command**

``` bash
nslookup networkwalks.com
```

**Observation:** The supplied output resolved `networkwalks.com` to
`192.232.216.135` using DNS server `8.8.8.8`.

**Evidence:**
[`03_NSLookup_DNS_Resolution.png`](Evidence/03_NSLookup_DNS_Resolution.png)

------------------------------------------------------------------------

### 4. curl --- HTTP Response Headers

**Command**

``` bash
curl -I https://networkwalks.com
```

**Observation:** The response returned `HTTP/2 200` and exposed standard
HTTP response-header information, including a WordPress REST API
reference.

**Evidence:**
[`04_Curl_HTTP_Response_Headers.png`](Evidence/04_Curl_HTTP_Response_Headers.png)

------------------------------------------------------------------------

### 5. Wafw00f --- WAF Detection

**Command**

``` bash
wafw00f networkwalks.com
```

**Observation:** The tool reported that the website is behind
**ModSecurity (SpiderLabs) WAF**.

**Evidence:**
[`05_Wafw00f_WAF_Detection.png`](Evidence/05_Wafw00f_WAF_Detection.png)

------------------------------------------------------------------------

### 6. DNSRecon --- DNS Enumeration

**Command**

``` bash
dnsrecon -d networkwalks.com
```

**Observation:** DNS information including SOA/NS, MX, A, TXT and SRV
records was enumerated in the supplied evidence.

**Evidence:**
[`06_DNSRecon_DNS_Enumeration.png`](Evidence/06_DNSRecon_DNS_Enumeration.png)

------------------------------------------------------------------------

## 🌐 Network Scanning with Zenmap

Zenmap, the graphical interface for Nmap, was used for controlled
network/service discovery.

### 7. Intense Scan --- scanme.nmap.org

The supplied evidence shows:

-   Target: `scanme.nmap.org`
-   Resolved address: `45.33.32.156`
-   Open TCP ports observed:
    -   `80/tcp`
    -   `443/tcp`
    -   `31337/tcp`
    -   `9929/tcp`

**Evidence:**
[`07_Zenmap_Intense_Scan.png`](Evidence/07_Zenmap_Intense_Scan.png)

### 8. Local Lab Topology

A separate Zenmap Quick Scan/topology view was captured for the local
lab target:

-   Target: `10.0.0.2`

**Evidence:**
[`08_Zenmap_Local_Lab_Topology.png`](Evidence/08_Zenmap_Local_Lab_Topology.png)

------------------------------------------------------------------------

## 📊 Security Relevance

The activities were primarily focused on **information gathering,
fingerprinting and network/service discovery**.

The observations should not automatically be treated as confirmed
vulnerabilities. Additional authorized validation would be required
before classifying any observation as an exploitable security
vulnerability.

### Key learning points

-   Reconnaissance helps build an initial picture of a target
    environment.
-   Technology/version disclosure can provide useful information to
    defenders and testers.
-   DNS records can reveal infrastructure and service relationships.
-   HTTP headers can expose useful implementation details.
-   WAF detection helps identify defensive controls.
-   Network scanning helps identify reachable hosts and exposed
    services.
-   Evidence and command documentation are important parts of a
    professional security assessment.

------------------------------------------------------------------------

## 📝 Recommendations

-   Keep CMS, plugins and supporting components updated.
-   Review publicly exposed technology/version information.
-   Minimize unnecessary technical information in HTTP responses.
-   Regularly review DNS records and remove obsolete services.
-   Keep WAF protections enabled, correctly configured and monitored.
-   Perform authorized network discovery regularly.
-   Investigate unexpected internal devices and services.
-   Maintain current network/service documentation.
-   Keep all reconnaissance and scanning within an approved scope.

------------------------------------------------------------------------

## 📂 Repository Structure

``` text
Aashif-B083-WK2-PENETRATION-TESTING/
│
├── README.md
│
├── Commands/
│   └── week2-commands.txt
│
├── Evidence/
│   ├── 01_WHOIS_Domain_Information.png
│   ├── 02_WhatWeb_Web_Technology_Fingerprinting.png
│   ├── 03_NSLookup_DNS_Resolution.png
│   ├── 04_Curl_HTTP_Response_Headers.png
│   ├── 05_Wafw00f_WAF_Detection.png
│   ├── 06_DNSRecon_DNS_Enumeration.png
│   ├── 07_Zenmap_Intense_Scan.png
│   └── 08_Zenmap_Local_Lab_Topology.png
│
└── Report/
    ├── Aashif_Rahman_Week2_Penetration_Testing_Report.docx
    └── Aashif_Rahman_Week2_Penetration_Testing_Report.pdf
```

------------------------------------------------------------------------

## 🔗 LinkedIn

I also documented this Week 2 learning activity on LinkedIn:

**LinkedIn Post:**\
https://www.linkedin.com/feed/update/urn:li:activity:7509244164849647617/

------------------------------------------------------------------------

## 👤 Author

**Aashif Rahman**\
B.Tech Information Technology\
Cybersecurity \| VAPT \| Network Security\
NetworkWalks Cybersecurity Program --- Batch B083

------------------------------------------------------------------------

## Disclaimer

This repository is for **educational cybersecurity training and
authorized lab work**. Do not use the commands, techniques or scanning
methodology against systems, networks or applications without explicit
authorization.
