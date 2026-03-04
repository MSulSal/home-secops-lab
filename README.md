# home-secops-lab

A reproducible defensive security monitoring stack for home and small-office networks.

## Scope

`home-secops-lab` focuses on defensive telemetry engineering:

- DNS visibility and query monitoring
- Network security monitoring with Zeek and Suricata
- Centralized logging with Loki and Promtail
- Dashboard-driven observability in Grafana
- Explainable anomaly detection over network telemetry
- Defensive incident response and hardening workflows

This repository is intentionally designed to run locally with Docker Compose and no paid services.

## Architecture At A Glance

Traffic and events are collected from:

- DNS service (Pi-hole or AdGuard Home)
- Zeek network logs
- Suricata alerts/events

Pipeline:

1. Collect telemetry at source systems
2. Ship logs with Promtail
3. Store/query logs in Loki
4. Visualize and investigate with Grafana
5. Run anomaly analysis from the `ml/` module on exported log data

## Repository Layout

- `docs/` architecture and operating guides
- `labs/` stepwise implementation labs
- `tooling/` Docker, configs, scripts, and dashboard assets
- `ml/` log parsers, feature engineering, model logic, and CLI analysis tooling
- `portfolio/` professional artifacts (architecture and case studies)

## Quick Start

1. Review [BOOTSTRAP.md](./BOOTSTRAP.md) for current stage and startup details.
2. Review [PROJECT_PLAN.md](./PROJECT_PLAN.md) for milestones.
3. Start stack from `tooling/docker`:

```bash
cd tooling/docker
docker compose up -d
```

4. Open Grafana at `http://localhost:3000` and validate log ingestion.

## Security and Ethics

This project is for defensive monitoring of systems and networks you own or are authorized to administer.
