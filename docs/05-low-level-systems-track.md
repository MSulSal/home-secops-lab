# Low-Level Systems Track

## Objective

Develop practical control from OS primitives up through network telemetry and detection, with no conceptual gaps at layer boundaries.

## Track Structure

## Track A - Linux Runtime Internals

Outcomes:

- inspect process, memory, and file descriptor state directly
- understand syscall-level behavior of userland programs

Core tools:

- `ps`, `top`, `htop`
- `/proc/<pid>/` inspection
- `strace`
- `lsof`

Evidence artifacts:

- process-tree baseline
- privileged-process inventory
- syscall trace notes for one networked process

## Track B - Socket and Packet Fundamentals

Outcomes:

- understand TCP/UDP socket lifecycle from code to packet
- map socket API behavior to observed traffic

Core tools:

- `ss`
- `tcpdump`
- `ip`

Programming exercises:

- C: minimal TCP client/server with explicit socket options
- Rust: equivalent client/server using `std::net` and async variant
- Zig: minimal socket program with explicit buffer handling

Evidence artifacts:

- code-level connection sequence notes
- packet capture proving expected handshake behavior
- socket-state timeline from `ss` during test runs

## Track C - Name Resolution and TLS Visibility

Outcomes:

- map DNS lookup behavior to outbound connection behavior
- separate transport metadata from encrypted payload content

Core tools:

- `dig`, `resolvectl` or `/etc/resolv.conf`
- `tcpdump` with DNS/TLS filters

Evidence artifacts:

- resolver path map
- encrypted-channel observability limits report

## Track D - Sensor Engineering

Outcomes:

- understand Zeek and Suricata data differences
- validate what each sensor can and cannot observe

Evidence artifacts:

- sensor coverage map
- blind-spot register

## Track E - Detection Engineering

Outcomes:

- convert raw telemetry into explainable anomalies
- tune for low noise and analyst utility

Evidence artifacts:

- feature schema
- detector output rationale document
- false-positive tuning notes

## Completion Standard

A track is complete only when:

1. command-level evidence exists
2. code-level evidence exists where applicable
3. an explicit attack-surface interpretation exists
