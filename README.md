# Week2-Penetration-Testing-Report
### Cybersecurity Internship | Reconnaissance, Footprinting & Network Scanning

![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-blue)
![Focus](https://img.shields.io/badge/Focus-Penetration%20Testing-red)
![Week](https://img.shields.io/badge/Internship-Week%2002-orange)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux%20%7C%20Windows-lightgrey)
## Overview

This repository documents the practical activities I completed during the second week of my cybersecurity internship.

The primary focus of this week's practical work was understanding how reconnaissance, footprinting, and network scanning are performed during the initial stages of a penetration test.

I worked with multiple reconnaissance tools in Kali Linux to collect publicly available information about a target domain. I also used Nmap through its graphical interface, Zenmap, to discover active hosts on my local network.

Throughout these exercises, I focused not only on executing commands but also on understanding the information returned by each tool, interpreting its security implications, and documenting the results with supporting evidence.

## Objectives

The main objectives of these practical exercises were:

- Understand the reconnaissance and footprinting phases of penetration testing.
- Gather publicly available information about a domain.
- Identify web technologies and services exposed by a website.
- Understand DNS records and domain resolution.
- Inspect HTTP response headers.
- Identify whether a Web Application Firewall (WAF) is present.
- Perform network discovery using Nmap and Zenmap.
- Identify active hosts within an authorized local network.
- Document observations, potential risks, and security recommendations.



# 3. Tools Used

The table below lists each tool used in this report and its purpose.

| Tool | Purpose |
|---|---|
| Kali Linux & Windows | Operating systems used for reconnaissance activities             |
| WHOIS                | Find domain registration details (owner, dates, name servers).   |
| whatweb              | Fingerprint web technologies (server, CMS, plugins, IP).         |
| nslookup             | Resolve the domain name to its IP address using DNS.             |
| curl -I              | Read the HTTP response headers of the website.                   |
| wafw00f              | Detect whether a Web Application Firewall protects the site.     |
| dnsrecon             | Enumerate all DNS records (NS, MX, SPF, TXT, SRV).               |
| Zenmap (Nmap GUI)    | Scan the local subnet to find live hosts, IPs and MAC addresses. |
| Windows CMD          | Local IP and MAC address identification                          |

# 4. Activities Performed

## 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux tools: **WHOIS, WhatWeb, Nslookup, Curl, Wafw00f 
and DNSRecon**. Each tool was used to collect a different type of information about the target.

First, I used **WHOIS** to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.

I then used **WhatWeb** to identify technologies used by the website. The results identified **WordPress 7.0.4** and **WP Download Manager 3.3.58**, along with other information exposed by the website.

Using **Nslookup**, I resolved the domain name to its IP address. The provided result identified **192.232.216.135**.

I used **Curl** with the `-I` option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint `/wp-json/`.

Next, I used **Wafw00f** to determine whether a Web Application Firewall was protecting the website. The result identified **ModSecurity (SpiderLabs)**.

Finally, I used **DNSRecon** to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

## 4.2 Network Scanning with Zenmap

For the second activity, I used **Zenmap** to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.
I first used the Windows `ipconfig` command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected **Ping Scan** to identify active hosts.

The example results provided in the practical identified hundred live hosts:
After completing the scan, I opened the **Topology** section in Zenmap, enabled the legend and saved the network topology in PDF format as required by the practical task.
## Security Observations and Risk Analysis

During the practical exercises, I observed several types of information that may be useful during a security assessment.

| Observation | Potential Security Implication |
|---|---|
| Domain registration information is publicly available. | Can assist an attacker in gathering organizational and infrastructure information. |
| Web technologies can be fingerprinted. | May help identify software components requiring further security review. |
| Domain IP addresses can be resolved. | Helps identify the network endpoint associated with a domain. |
| HTTP response headers reveal technical information. | May assist further application fingerprinting. |
| WAF technology can be identified. | Provides insight into some aspects of the website's defensive architecture. |
| Active hosts can be discovered on a local network. | Helps establish an initial view of the network's connected devices. |

**Important:** These are reconnaissance observations and potential security considerations, not confirmed vulnerabilities. Additional authorized testing is necessary to establish whether any actual security weakness exists.

## Recommendations

Based on the observations from these practical exercises, I identified the following general security recommendations:

1. Review publicly exposed information about web technologies and infrastructure.
2. Keep website platforms, plugins, and components updated.
3. Review HTTP response headers and minimize unnecessary technical information disclosure.
4. Regularly review DNS records and remove obsolete or unnecessary entries.
5. Properly configure and monitor Web Application Firewall rules.
6. Conduct periodic internal network discovery.
7. Investigate unexpected devices connected to organizational networks.
8. Maintain updated network documentation and asset inventories.

## Evidence and Screenshots

I have included screenshots from the practical exercises to document the commands executed and the outputs obtained.

The evidence directory contains the following activities:

| Evidence | Activity |
|---|---|
| 1 | WHOIS lookup |
| 2 | WhatWeb fingerprinting |
| 3 | Nslookup DNS resolution |
| 4 | Curl HTTP response inspection |
| 5 | Wafw00f detection |
| 6 | DNSRecon enumeration |
| 7 | Zenmap network scan |
| 8 | Zenmap network discovery and topology |

Screenshots are stored in the `screenshots/` directory.

## Key Learning Outcomes

Through these activities, I developed a better understanding of the initial stages of penetration testing.

Some of the important things I learned include:

- How publicly available information can contribute to reconnaissance.
- How different tools collect different types of information about a target.
- How DNS resolution and DNS enumeration work.
- How to identify web technologies through fingerprinting.
- How HTTP response headers provide information about web servers.
- How to identify detectable WAF technologies.
- How Nmap performs host discovery.
- How Zenmap can visualize discovered network devices.
- Why evidence collection and proper technical documentation are important in security assessments.

Most importantly, I learned that reconnaissance is not simply about running tools and collecting outputs. It requires understanding what the results mean, determining whether an observation represents a genuine security concern, and documenting conclusions accurately.

## Conclusion

Week 2 gave me practical exposure to the reconnaissance, footprinting, and network discovery stages of penetration testing.

By working with WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon, Nmap, and Zenmap, I gained experience collecting and interpreting information from both web-facing infrastructure and a local network.

These activities helped strengthen my understanding of how penetration testers approach an environment before moving into deeper security assessment activities.

I also gained experience organizing technical evidence, identifying potential security implications, and presenting observations through a structured penetration testing report.

This repository represents my practical learning and documentation from Week 2 of my cybersecurity internship.

---

## Authorization and Disclaimer

All testing activities documented in this repository were performed as part of educational cybersecurity practicals and within the applicable authorized scope.

The information is provided for educational and learning purposes only. Reconnaissance and network scanning should only be performed on systems and networks for which appropriate authorization has been obtained.

I do not support or encourage unauthorized access, scanning, or misuse of cybersecurity tools.

---

**Documented by:** Maryam Zafar 
**Internship Module:** Week 2  
**Domain:** Cybersecurity & Ethical Hacking  
**Repository:** Week-2-Penetration-Testing-Report
