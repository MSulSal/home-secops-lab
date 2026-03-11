# Lab 00 - Node Baseline Runbook

## Goal

Establish a trusted baseline for a Kali WSL node before automation and detection engineering.

## Prerequisites

- Kali environment available
- terminal access as current user
- `sudo` privileges for packet capture step

## Procedure

Run each block in order.

### 1) User and Privilege Context

```bash
whoami
id
groups
```

Record:

- active user identity
- privilege-bearing groups

### 2) System Context

```bash
uname -a
cat /etc/os-release
cat /proc/version
```

Record:

- kernel version
- distro version
- WSL indicators

### 3) Network Interface and Route Baseline

```bash
ip -brief addr
ip route
```

Record:

- active interfaces
- default route interface and gateway

### 4) DNS Baseline

```bash
cat /etc/resolv.conf
```

Record:

- configured resolver IPs

### 5) Listening Service Baseline

```bash
ss -tulpen
```

Record:

- all listening ports
- owning process and whether expected

### 6) Active Connection Baseline

```bash
ss -tpn
```

Record:

- external peers
- associated process names

### 7) Packet Sample Baseline

```bash
sudo tcpdump -i any -nn -c 20
```

Record:

- common protocol types
- repeated destination patterns
- any unknown traffic

## Acceptance Criteria

- baseline command outputs captured
- primary outbound interface identified
- resolver set identified
- unexpected listening services documented
- first attack-surface summary drafted

## Deliverable

Use [node-baseline-report-template.md](../docs/templates/node-baseline-report-template.md) to produce the baseline report.
