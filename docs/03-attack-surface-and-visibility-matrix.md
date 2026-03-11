# Attack Surface and Visibility Matrix

## Goal

Track what can be attacked, what can be observed, and what remains blind in current deployment state.

## Matrix

| Layer | Surface | Typical Abuse Path | Defensive Telemetry | Blind Spots | Planned Control |
|---|---|---|---|---|---|
| Firmware/Boot | Boot chain and firmware state | Offline tampering or insecure boot configuration | Boot config records, hardware inventory notes | Direct firmware integrity without external attestations | Secure boot review, disk encryption policy |
| OS Privilege | Local user and privilege boundaries | Credential theft, privilege escalation | `id`, `groups`, auth logs, process ownership | Kernel-level rootkits evade userland checks | Least privilege and patch cadence |
| Local Services | Listening ports and daemons | Remote exploitation of exposed service | `ss -tulpen`, service configs, local firewall state | Service on loopback still exploitable by local malware | Service minimization and bind restrictions |
| Outbound Network | Egress channels | Data exfiltration and C2 | `ss -tpn`, flow telemetry, DNS logs | Encrypted payload content | Egress allow-list and anomaly monitoring |
| DNS | Resolver path and domain lookups | DGA, beaconing, tunneling patterns | DNS query logs and response codes | Encrypted DNS without local resolver visibility | Local resolver logging and rare-domain detection |
| NSM Sensors | Packet and event collection points | Traffic designed to bypass sensor placement | Zeek logs, Suricata events | Unseen segments and non-mirrored paths | Sensor placement validation |
| Log Pipeline | Ingestion and storage plane | Log tampering or ingestion outage | Promtail health, Loki labels and query checks | Loss before shipper collection | Health checks, retention checks, alerting |
| Detection Logic | Rules and anomaly models | Evasion through low-and-slow behavior | Detection outputs and tuning records | Novel behavior with low signal strength | Multi-signal correlation and periodic tuning |

## Review Cadence

- update after each milestone completion
- explicitly record newly closed blind spots
- explicitly record unresolved blind spots
