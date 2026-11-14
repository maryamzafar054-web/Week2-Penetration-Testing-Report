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
