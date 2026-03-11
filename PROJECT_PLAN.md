# PROJECT_PLAN

## Mission

Develop operator-level understanding of system and network behavior while implementing a production-style defensive monitoring pipeline.

## Phase Model

## Phase 0 - Operational Foundations

Outcome:

- terminal fluency
- Linux process/network inspection fluency
- baseline evidence capture discipline

Deliverables:

- terminal foundations doc
- node baseline runbook
- baseline report template

## Phase 1 - Host Visibility

Outcome:

- repeatable host baseline collection
- first hardening backlog

Deliverables:

- scripted baseline capture
- artifact normalization format
- host attack-surface report v1

## Phase 2 - DNS Visibility

Outcome:

- DNS telemetry ingestion and triage
- rare-domain and query-volume baseline

Deliverables:

- DNS source integration design
- parser/output schema
- DNS investigation playbook

## Phase 3 - Network Security Monitoring

Outcome:

- Zeek + Suricata telemetry capture
- sensor placement and blind-spot analysis

Deliverables:

- sensor config package
- log ingestion mapping
- alert triage workflow

## Phase 4 - Centralized Logging and Observability

Outcome:

- Loki + Promtail + Grafana stack operational
- cross-source investigation workflows

Deliverables:

- compose and config bundle
- dashboard pack
- operational runbook

## Phase 5 - Detection Engineering

Outcome:

- explainable anomaly scoring across DNS, Zeek, and Suricata data

Deliverables:

- feature pipeline
- periodicity detection
- EWMA deviation detector
- Isolation Forest scoring and report output

## Phase 6 - Defensive Response and Hardening

Outcome:

- incident response procedures with measurable closure criteria

Deliverables:

- playbook suite
- control validation checklist
- post-incident hardening matrix

## Planning Source of Truth

Execution order is tracked in `docs/04-commit-by-commit-plan.md`.
