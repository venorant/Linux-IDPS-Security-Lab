
# Linux Intrusion Detection & Prevention System

## Overview
A Linux-based security lab designed to detect suspicious network activity, monitor failed authentication attempts, and prevent unauthorized access.

## Technologies
- **OS:** Debian 13
- **Virtualization:** VirtualBox
- **Networking:** NAT, Internal Network, IPv4
- **Security Tools (Planned):** Fail2Ban, Suricata, nftables
- **Remote Access (Planned):** OpenSSH

## Network Architecture

| Machine | Role | Interface | IP Address |
|---------|------|-----------|------------|
| IDPS | Protected Server (NAT) | enp0s3 | 10.0.2.15/24 |
| IDPS | Protected Server (LAN) | enp0s8 | 192.168.50.10/24 |
| IDPSC | Testing Client | enp0s3 | 192.168.50.20/24 |

- **Internal Network:** IDPS_LAB
- **Internal Subnet:** 192.168.50.0/24
- **NAT Gateway:** 10.0.2.2

IDPS uses NAT for Internet access, while IDPSC communicates with IDPS through the isolated internal network.

## Implementation & Progress

### 1. Network Infrastructure — Completed
Established a virtual security lab using two Debian 13 machines.

- Configured NAT and isolated internal networking.
- Assigned persistent IPv4 addresses using NetworkManager.
- Verified network connectivity, Internet access, and DNS resolution.

### 2. SSH Protection — Upcoming
Implement automated protection against unauthorized SSH access.

- Configure OpenSSH and Fail2Ban.
- Monitor authentication failures and automatically ban suspicious IPs.
- Validate blocking mechanisms through controlled login attempts.

### 3. Network Intrusion Detection — Planned
Deploy Suricata to identify suspicious network traffic.

- Configure network monitoring and detection rules.
- Generate and analyze security alerts.
- Examine network activity from the testing client.

### 4. Intrusion Prevention & Validation — Planned
Strengthen network security and evaluate the implemented controls.

- Configure nftables firewall rules.
- Integrate detection and prevention mechanisms.
- Analyze logs, verify security responses, and document results.