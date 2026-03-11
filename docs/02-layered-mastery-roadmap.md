# Layered Mastery Roadmap

## Objective

Build a bottom-up mental model from hardware-adjacent constraints through application telemetry and detection engineering.

## Layer 0 - Hardware and Firmware Boundary

Understand:

- trust assumptions for physical device access
- boot chain, firmware integrity, and disk protection controls
- limits of software-only observability when hardware is out of trust

Output artifact:

- documented trust boundary assumptions for the monitored node

## Layer 1 - Kernel and OS Primitives

Understand:

- processes, threads, memory maps, syscalls, capabilities
- user/group model and privilege transitions
- filesystem permissions and mount semantics

Terminal proof:

- `ps`, `top`, `id`, `groups`, `mount`, `/proc` inspection

Output artifact:

- host privilege and process exposure map

## Layer 2 - Network Stack Internals

Understand:

- interface lifecycle, routes, ARP/neighbor behavior
- TCP/UDP socket states and connection lifecycle
- NAT and WSL network translation limits

Terminal proof:

- `ip`, `ss`, `tcpdump`

Output artifact:

- host egress map and listener inventory

## Layer 3 - Name Resolution and Encrypted Transport

Understand:

- DNS resolution path and failure modes
- TLS metadata visibility limits without decryption
- what remains observable when payload is encrypted

Output artifact:

- DNS telemetry schema and triage criteria

## Layer 4 - Sensor Engineering

Understand:

- Zeek vs Suricata data models
- sensor placement tradeoffs and blind spots
- packet loss and clock/timestamp reliability

Output artifact:

- sensor deployment and coverage matrix

## Layer 5 - Log Pipeline Engineering

Understand:

- ingestion, labeling, retention, query cost
- schema consistency across sources
- durability and failure handling

Output artifact:

- centralized logging architecture and operational checks

## Layer 6 - Detection Engineering

Understand:

- baseline behavior modeling
- anomaly detection tradeoffs and explainability
- false positive control and analyst workflow

Output artifact:

- scored anomaly report with rationale per finding

## Layer 7 - Response and Hardening

Understand:

- triage decision points
- containment and recovery sequencing
- control validation after remediation

Output artifact:

- response playbooks and hardening backlog
