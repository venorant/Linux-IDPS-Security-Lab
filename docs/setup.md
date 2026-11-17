# Lab Setup

## VirtualBox Network Configuration

| Machine | Adapter | Network | Interface | IP Address |
|---------|---------|---------|-----------|------------|
| IDPS | 1 | NAT | enp0s3 | 10.0.2.15/24 |
| IDPS | 2 | Internal (IDPS_LAB) | enp0s8 | 192.168.50.10/24 |
| IDPSC | 1 | Internal (IDPS_LAB) | enp0s3 | 192.168.50.20/24 |

## NetworkManager Configuration

### IDPS — Server

```bash
sudo nmcli connection modify enp0s8
  ipv4.method manual
  ipv4.addresses 192.168.50.10/24
  ipv4.never-default yes
  connection.autoconnect yes

sudo nmcli connection up enp0s8
```

### IDPSC — Client

```bash
sudo nmcli connection modify enp0s3
  ipv4.method manual
  ipv4.addresses 192.168.50.20/24
  ipv4.never-default yes
  connection.autoconnect yes

sudo nmcli connection up enp0s3
```