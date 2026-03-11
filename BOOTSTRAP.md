# BOOTSTRAP

## Purpose

Build a reproducible defensive security monitoring lab from first principles, starting with host-node observability in Kali WSL and expanding to full pipeline telemetry (DNS, Zeek, Suricata, Loki, Grafana, anomaly analysis).

## Current Stage

Stage: `S0-foundation`

Status:

- documentation-first foundation established
- terminal fundamentals documented
- host baseline runbook documented
- attack-surface baseline method documented

## Environment Baseline

- Primary build environment: Kali Linux in WSL
- Host environment: Windows + WSL virtualization boundary
- Initial visibility scope: monitored node first, full-network visibility later via dedicated sensor placement

## Repository Map

- `README.md`: high-level index and project scope
- `BOOTSTRAP.md`: resume entrypoint if context is lost
- `PROJECT_PLAN.md`: phase-level goals and completion criteria
- `docs/`: architecture, roadmap, attack surface, and execution planning
- `labs/`: concrete runbooks and verification tasks
- `docs/templates/`: reusable reporting templates
- `notes_private/`: private notes (gitignored)

## Resume Procedure

1. Read `README.md`
2. Read `PROJECT_PLAN.md`
3. Open `docs/04-commit-by-commit-plan.md`
4. Execute the next unchecked commit unit
5. Update `docs/06-delivery-ledger.md` and `docs/07-decision-log.md`

## Active Milestone

Milestone: `M1-node-baseline`

Completion criteria:

- baseline command outputs captured
- primary egress path identified
- DNS resolver path identified
- listening services reviewed
- first attack-surface report completed

## Next Milestones

1. `M2-host-telemetry`: scripted baseline capture and normalized output
2. `M3-dns-visibility`: DNS log ingestion and query triage workflow
3. `M4-nsm-sensors`: Zeek and Suricata integration
4. `M5-central-logging`: Loki/Promtail/Grafana operational
5. `M6-detection`: explainable anomaly analysis module
6. `M7-response`: defensive playbooks and hardening controls
