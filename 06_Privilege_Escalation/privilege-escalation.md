# Privilege Escalation

## Main Statement

After obtaining access to the Drupal web server, the next objective was escalating privileges from the web server user to the **root** user. This phase focused on Linux privilege escalation through system enumeration and SUID permission analysis.

---

## Objective

* Enumerate local privilege escalation opportunities.
* Identify SUID binaries.
* Investigate installed binaries and versions.
* Gain root access through a privilege escalation technique.

---

## Step 1 — Check Sudo Permissions

The first privilege escalation check was reviewing sudo permissions.

### Command

```bash id="hq0zhj"
sudo -l
```

### Why This Command?

Displays commands that the current user can execute with elevated privileges.

### Observation

No useful sudo permissions were available for the compromised user.

---

## Step 2 — Enumerate SUID Binaries

The next step was searching for binaries running with the SUID permission.

### Command

```bash id="j6gyvk"
find / -perm -u=s -type f 2>/dev/null
```

### Why This Command?

Searches the filesystem for binaries with the SUID bit enabled.

### Observation

Several SUID binaries were discovered during enumeration.

**Screenshot Location**

```text id="gzdijw"
assets/images/suid-enumeration.png
```

---

## Step 3 — Identify Interesting Binaries

Among the discovered binaries, one executable appeared unusual compared to default Linux installations.

### Observation

The binary was investigated further because it was running with elevated permissions.

---

## Step 4 — Check Binary Version

### Command

```bash id="mylkag"
/usr/sbin/exim4 --version
```

### Purpose

Displays the installed version of the executable for vulnerability investigation.

### Observation

The installed version was compared with publicly available vulnerability information.

---

## Step 5 — Research Privilege Escalation Opportunity

The identified binary version was researched using publicly available security resources.

### Resources Used

* Exploit-DB
* GTFOBins

### Observation

A privilege escalation technique was available for the identified binary.

> **Security Note:** The exploit commands are intentionally omitted from this public repository.

---

## Step 6 — Verify Root Access

After performing the privilege escalation technique, root access was verified.

### Commands

```bash id="fgsudg"
whoami
cd /root
ls
```

### Observation

The current user changed to **root**, confirming successful privilege escalation.

**Screenshot Location**

```text id="hdu26q"
assets/images/root-access.png
```

---

## Privilege Escalation Summary

| Activity                 | Result     |
| ------------------------ | ---------- |
| Sudo Enumeration         | Completed  |
| SUID Enumeration         | Completed  |
| Binary Investigation     | Completed  |
| Version Research         | Completed  |
| Root Access Verification | Successful |

---

## Key Learning

* SUID binaries are common privilege escalation targets.
* Linux enumeration should always include permission analysis.
* Public resources like GTFOBins help understand privilege escalation techniques during security research.
