# Enumeration

## Main Statement

Enumeration is the process of collecting detailed information about the target after confirming it is reachable. During this phase, services, directories, files, and application-specific information were identified to prepare for exploitation.

---

## Objective

* Identify running services.
* Detect the CMS version.
* Discover hidden directories.
* Review publicly accessible resources.

---

## Step 1 — Network Service Enumeration

The first scan identified open ports and service versions.

### Command

```bash
nmap -sC -sV -O -T4 -p- <TARGET-IP>
```

### Purpose

| Option | Description              |
| ------ | ------------------------ |
| `-sC`  | Run default NSE scripts. |
| `-sV`  | Detect service versions. |
| `-O`   | Detect operating system. |
| `-T4`  | Faster scan timing.      |
| `-p-`  | Scan all ports.          |

### Observation

The scan revealed:

* Apache HTTP Server
* SSH Service
* Drupal CMS
* Debian Linux operating system

**Screenshot Location**

```text
assets/images/nmap-scan.png
```

---

## Step 2 — Directory Enumeration

After identifying the web service, hidden directories were enumerated.

### Command

```bash
gobuster dir -u http://<TARGET-IP> \
-w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt \
-x php,html,txt
```

### Purpose

Discovers hidden directories and files that are not visible through the homepage.

### Observation

Important directories returned successful responses.

| Directory   | Observation                |
| ----------- | -------------------------- |
| install.php | Installation page exposed. |
| includes    | Drupal application files.  |
| modules     | Installed Drupal modules.  |
| profiles    | Installation profiles.     |
| scripts     | Drupal script directory.   |

**Screenshot Location**

```text
assets/images/gobuster-scan.png
```

---

## Step 3 — Review Accessible Resources

The discovered pages were manually inspected.

### Observation

The installation page exposed Drupal setup information, indicating that installation resources were still available.

---

## Step 4 — Source Code Review

The HTML source code of the website was inspected for useful information.

### Observation

The page source revealed Drupal-related paths and application structure that assisted further enumeration.

---

## Step 5 — Inspect robots.txt

### Resource

```text
http://<TARGET-IP>/robots.txt
```

### Observation

The robots.txt file exposed several restricted directories belonging to the Drupal application.

**Screenshot Location**

```text
assets/images/robots-txt.png
```

---

## Enumeration Summary

| Enumeration Activity   | Result    |
| ---------------------- | --------- |
| Service Enumeration    | Completed |
| Version Detection      | Completed |
| Directory Enumeration  | Completed |
| Source Code Inspection | Completed |
| robots.txt Analysis    | Completed |

---

## Key Learning

* Enumeration is one of the most important phases of penetration testing.
* Public files like robots.txt may expose sensitive application paths.
* Hidden directories often reveal installation files and configuration resources that become useful during exploitation.
