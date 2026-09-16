# Security Findings and Remediation

## Main Statement

The penetration testing assessment identified several security weaknesses that allowed the attacker to progress from reconnaissance to complete system compromise. Each finding is paired with a practical remediation recommendation.

---

# Security Findings

## Finding 1 — Drupal Installation Page Exposed

### Severity

**Medium**

### Description

The Drupal installation page was publicly accessible and revealed information about the application setup.

### Risk

* Information disclosure.
* Drupal fingerprinting.
* Exposure of installation resources.

### Recommendation

* Remove installation pages after deployment.
* Restrict access to installation resources.

---

## Finding 2 — Sensitive Directories Exposed in robots.txt

### Severity

**Low**

### Description

The robots.txt file exposed multiple internal Drupal directories.

### Risk

Attackers can identify administrative and configuration paths without authentication.

### Recommendation

* Avoid exposing sensitive application paths through robots.txt.
* Restrict sensitive directories using server configuration.

---

## Finding 3 — Database Credentials Stored in Configuration File

### Severity

**Critical**

### Description

The Drupal configuration file contained database connection information.

### Risk

An attacker with server access can authenticate directly to the database.

### Recommendation

* Restrict read permissions on configuration files.
* Store secrets securely.
* Apply least privilege permissions.

---

## Finding 4 — Drupal Remote Code Execution

### Severity

**Critical**

### Description

A vulnerable Drupal installation allowed remote code execution through a publicly available exploit.

### Risk

Attackers can obtain shell access without valid user credentials.

### Recommendation

* Update Drupal to supported versions.
* Patch known vulnerabilities immediately.
* Remove vulnerable modules.

---

## Finding 5 — Privilege Escalation Through SUID Binary

### Severity

**High**

### Description

A privileged executable allowed local privilege escalation after server compromise.

### Risk

Attackers can obtain root privileges.

### Recommendation

* Audit SUID binaries regularly.
* Remove unnecessary SUID permissions.
* Apply security updates for vulnerable packages.

---

# Overall Risk Assessment

<table><table-section header><table-row header><table-cell header>Security Area</table-cell><table-cell header>Risk Level</table-cell></table-row></table-section><table-row><table-cell>Web Application Configuration</table-cell><table-cell>High</table-cell></table-row><table-row><table-cell>Information Disclosure</table-cell><table-cell>Critical</table-cell></table-row><table-row><table-cell>Database Security</table-cell><table-cell>Critical</table-cell></table-row><table-row><table-cell>Linux Privilege Management</table-cell><table-cell>High</table-cell></table-row><table-row><table-cell>Patch Management</table-cell><table-cell>Critical</table-cell></table-row></table>

---

# Remediation Summary

## Web Application Security

* Remove unused installation resources.
* Disable directory listing.
* Restrict configuration files.
* Keep Drupal updated.

## Server Hardening

* Audit SUID permissions.
* Apply operating system security updates.
* Remove unnecessary packages.
* Enforce least privilege permissions.

## Database Security

* Protect configuration files.
* Use strong database credentials.
* Limit database user permissions.
* Avoid storing secrets in publicly readable locations.

## Monitoring Recommendations

* Enable Apache access logs.
* Monitor authentication attempts.
* Review privilege escalation events.
* Monitor configuration file access.

---

# Lessons Learned

This lab demonstrated how multiple small security weaknesses can be chained together to achieve complete system compromise. Strong configuration management, patch management, and privilege management significantly reduce this attack surface.
