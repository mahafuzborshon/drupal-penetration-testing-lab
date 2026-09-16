# Reconnaissance

## Main Statement

Reconnaissance is the first stage of penetration testing. Before interacting with the target, it is important to identify the network interface, discover active hosts, and verify that the target machine is reachable.

This phase helped identify the vulnerable Drupal server inside the VMware network.

---

## Objective

* Identify the local network interface.
* Discover active devices on the subnet.
* Verify the target machine is online.

---

## Step 1 — Identify the Local Network Interface

The first task was identifying the active interface on Kali Linux.

### Command

```bash
ifconfig
```

### Purpose

Displays network interfaces and their assigned IP addresses.

### Observation

The active Ethernet interface (`eth0`) contained the IP address assigned to Kali Linux, which was later used for network discovery.

**Screenshot Location**

```text
assets/images/target-discovery.png
```

---

## Step 2 — Discover Live Hosts on the Network

After identifying the interface, the local subnet was scanned.

### Command

```bash
netdiscover -i eth0 -r 192.168.1.0/24
```

### Purpose

Scans the local network and lists active hosts with their IP addresses and MAC addresses.

### Observation

Several hosts were detected, and one machine was identified as the Drupal target.

**Screenshot Location**

```text
assets/images/target-discovery.png
```

---

## Step 3 — Verify Target Availability

Before performing service enumeration, the target host was tested for connectivity.

### Command

```bash
ping <TARGET-IP>
```

### Purpose

Confirms that the target machine is alive and reachable.

### Observation

The target responded successfully, confirming network connectivity.

---

## Reconnaissance Summary

| Activity                         | Result    |
| -------------------------------- | --------- |
| Local Interface Identification   | Completed |
| Host Discovery                   | Completed |
| Target Reachability Verification | Completed |

---

## Key Learning

* Always identify the correct network interface before scanning.
* Host discovery helps isolate the target machine from other devices.
* Connectivity verification prevents unnecessary scanning errors later in the assessment.
