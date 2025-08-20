## OSINT Task – Subdomain Enumeration & Reconnaissance
## Introduction

## Objective

The goal of this task is to perform subdomain enumeration on a target domain using OSINT techniques and publicly available tools, and then analyze the results to identify possible entry points for further reconnaissance.

## Methodology
1. Passive Subdomain Enumeration

Tools Used:

crt.sh (Certificate Transparency logs)

Sublist3r

Amass

Assetfinder

Process:

Queried certificate transparency logs via crt.sh.

Used Sublist3r and Amass to gather subdomains from multiple public sources.

Collected additional subdomains using assetfinder.

2. Active Subdomain Validation

Verified the discovered subdomains by resolving DNS records with:

dig / nslookup

dnsx (for mass resolution)

3. Port Scanning & Service Detection

Ran Nmap to scan for open ports on active subdomains.

Identified running services (HTTP, HTTPS, SSH, FTP, etc.).

4. Vulnerability Assessment (Lightweight)

Checked for default pages, open directories, and outdated technologies using:

httpx

whatweb

## Results

Target Domain: example.com

Discovered Subdomains (sample):

mail.example.com
dev.example.com
staging.example.com
api.example.com


Interesting Findings:

dev.example.com exposed a login panel with default banner text.

staging.example.com was running outdated Apache version.

## Mitigation Recommendations

Implement DNS monitoring to detect newly registered/visible subdomains.

Regularly review and decommission staging/dev environments.

Apply strict access controls and authentication on sensitive subdomains.

Keep all exposed services and frameworks up to date.

## Conclusion

This OSINT exercise demonstrates how subdomain enumeration provides valuable insights into a target’s attack surface. Even publicly available information can uncover hidden systems that, if not properly secured, may pose serious risks. Subdomain reconnaissance should always be a first step in any security assessment or penetration test.

