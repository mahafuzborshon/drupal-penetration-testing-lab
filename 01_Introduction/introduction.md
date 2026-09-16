# Introduction

## Main Statement

This lab documents the complete penetration testing process of a vulnerable **Drupal Content Management System (CMS)** hosted inside a VMware laboratory environment. The assessment follows a practical offensive security workflow, starting with target discovery and ending with root privilege escalation on the Linux server.

The objective was not only to exploit the application but also to understand how misconfigurations and exposed information can lead to full system compromise.

---

## Lab Objective

The primary objective of this penetration testing lab was to identify vulnerabilities in a Drupal web server and document every stage of the attack lifecycle.

### Objectives Completed

* Discover the target machine inside the local network.
* Perform network reconnaissance.
* Enumerate running services and hidden directories.
* Exploit a vulnerable Drupal installation.
* Obtain remote shell access.
* Discover sensitive configuration files.
* Access the Drupal MySQL database.
* Perform Linux privilege escalation.
* Gain root-level access.

---

## Lab Environment

| Component        | Details               |
| ---------------- | --------------------- |
| Attacker Machine | Kali Linux            |
| Target Machine   | Drupal CMS Server     |
| Operating System | Debian Linux          |
| Virtualization   | VMware Workstation    |
| Network          | Local Bridged Network |

---

## Attack Lifecycle

This lab followed a structured penetration testing methodology.

| Phase                | Goal                                                      |
| -------------------- | --------------------------------------------------------- |
| Reconnaissance       | Discover and verify the target machine.                   |
| Enumeration          | Collect information about services and web resources.     |
| Exploitation         | Execute a Drupal Remote Code Execution vulnerability.     |
| Post Exploitation    | Investigate configuration files and database credentials. |
| Privilege Escalation | Obtain root privileges on the server.                     |

---

## Tools Used During the Lab

| Tool                 | Purpose                                  |
| -------------------- | ---------------------------------------- |
| Netdiscover          | Host discovery on the local network.     |
| Nmap                 | Network and service enumeration.         |
| Gobuster             | Directory and file enumeration.          |
| Searchsploit         | Vulnerability discovery.                 |
| Metasploit Framework | Exploitation of Drupal vulnerability.    |
| MySQL Client         | Database authentication and enumeration. |
| GTFOBins             | Privilege escalation reference.          |

---

## Expected Learning Outcome

After completing this lab, I was able to understand how reconnaissance, enumeration, exploitation, information disclosure, database enumeration, and privilege escalation work together during a real penetration testing engagement.
