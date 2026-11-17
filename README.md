# Linux Intrusion Detection & Prevention System (IDPS)

## Overview
A Debian 13 security lab built in VirtualBox to implement and evaluate intrusion detection and prevention mechanisms.

## Technologies
- Debian 13
- Oracle VirtualBox
- NetworkManager
- OpenSSH
- Fail2Ban
- nftables

## Architecture
The lab consists of two Debian virtual machines:

- **IDPS:** Protected server with NAT Internet access.
- **IDPSC:** Testing client connected to the server through an isolated internal network (**IDPS_LAB**).

## Implementation
- Created and configured both virtual machines.
- Established NAT and isolated internal networking.
- Configured persistent static IPv4 addresses using NetworkManager.
- Configured SSH access between the client and server.
- Implemented automatic SSH intrusion prevention using Fail2Ban and nftables.
- Validated IP blocking after repeated failed authentication attempts.

## Documentation
- [Lab Setup](docs/setup.md)