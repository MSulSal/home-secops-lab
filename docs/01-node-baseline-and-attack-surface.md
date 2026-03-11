# Node Baseline and Attack Surface

## Objective

Build a defensible baseline for one monitored node before deploying automated telemetry pipelines.

## Method

For each command and artifact:

1. Define the asset being observed.
2. Identify reachable attack surface.
3. Capture telemetry signal.
4. Interpret risk and expected behavior.
5. Record follow-up hardening actions.

## Baseline Command Set

### Identity and Privilege Context

```bash
whoami
id
groups
```

Why: user privilege level determines compromise impact and available attacker actions.

Review:

- account name
- UID/GID
- privileged group memberships (for example, `sudo`)

### OS and Kernel Context

```bash
uname -a
cat /etc/os-release
cat /proc/version
```

Why: environment type (WSL vs bare metal) affects telemetry placement and visibility.

Review:

- kernel version and architecture
- distribution and release
- virtualization boundary indicators

### Interface and Addressing

```bash
ip -brief addr
ip route
```

Why: identifies ingress/egress interfaces and primary outbound path.

Review:

- active interfaces
- assigned IPv4/IPv6 addresses
- default route (`default via ... dev ...`)

### DNS Resolver Context

```bash
cat /etc/resolv.conf
```

Why: DNS resolution path is critical for beaconing, rare domain, and exfiltration detection.

Review:

- resolver IPs (`nameserver`)
- search domains/options

### Listening Services

```bash
ss -tulpen
```

Why: listening sockets are direct host attack surface.

Review:

- local bind addresses and ports
- owning process/service
- unexpected listeners

### Active Outbound Connections

```bash
ss -tpn
```

Why: exposes current communication peers and potential suspicious egress.

Review:

- remote destinations
- process-to-destination mapping

### Packet-Level Reality Check

```bash
sudo tcpdump -i any -nn -c 20
```

Why: validates real network behavior independent of application logs.

Review:

- protocol and flow patterns
- unknown destinations
- repeated periodic communications

## WSL-Specific Considerations

- WSL is excellent for host-level telemetry development.
- WSL does not automatically provide full home-network visibility.
- Full network security monitoring requires a sensor position with traffic access (gateway, mirror/SPAN, or TAP).

## Output Requirements

After each baseline run, preserve:

- command outputs
- analyst interpretation
- explicit expected-vs-unexpected findings
- hardening actions to be executed next
