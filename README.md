# Drupal Penetration Testing Lab

A complete penetration testing documentation of a vulnerable **Drupal CMS** machine performed inside a controlled VMware laboratory environment using Kali Linux.

This repository documents every phase of the penetration testing process, including reconnaissance, enumeration, exploitation, information disclosure, database enumeration, privilege escalation, and remediation.

> **Educational Purpose:** This project was completed in an isolated lab environment for cybersecurity learning and documentation.

---

## Lab Overview

The objective of this lab was to compromise a vulnerable Drupal web application without any initial credentials and document the complete attack lifecycle.

### Objectives

* Discover the target machine.
* Enumerate network services.
* Identify hidden web directories.
* Exploit a Drupal vulnerability.
* Obtain shell access.
* Investigate sensitive configuration files.
* Access the Drupal database.
* Perform privilege escalation.
* Gain root access.

---

## Attack Lifecycle

| Phase                | Description                                  |
| -------------------- | -------------------------------------------- |
| Reconnaissance       | Target identification and host verification. |
| Enumeration          | Service scanning and directory discovery.    |
| Exploitation         | Drupal Remote Code Execution.                |
| Post Exploitation    | Configuration and database enumeration.      |
| Privilege Escalation | Root access through Linux misconfiguration.  |
| Remediation          | Security recommendations and hardening.      |

---

## Tools Used

* Kali Linux
* VMware Workstation
* Netdiscover
* Nmap
* Gobuster
* Searchsploit
* Metasploit Framework
* MySQL Client
* GTFOBins
* Linux Enumeration Commands

---

## Repository Structure

```text
01_Introduction/
02_Reconnaissance/
03_Enumeration/
04_Exploitation/
05_Post_Exploitation/
06_Privilege_Escalation/
07_Findings_And_Remediation/
assets/images/
report/
```

---

## Skills Demonstrated

* Network Reconnaissance
* Service Enumeration
* Web Directory Enumeration
* Drupal Vulnerability Assessment
* Remote Code Execution
* Information Disclosure
* Database Enumeration
* Linux Privilege Escalation
* Security Documentation
