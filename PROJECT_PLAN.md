# PROJECT_PLAN

## Phase 1 - Visibility

### Goals

- Baseline network inventory and expected traffic patterns
- DNS logging enabled and retained for analysis

### Deliverables

- `labs/lab01-baseline-network.md`
- `labs/lab02-dns-monitoring.md`
- Initial DNS dashboard panels

## Phase 2 - Network Security Monitoring

### Goals

- Deploy Zeek for network telemetry
- Deploy Suricata for IDS/alert visibility

### Deliverables

- `labs/lab03-network-capture.md`
- `labs/lab04-zeek-analysis.md`
- `labs/lab05-suricata-alerts.md`

## Phase 3 - Central Logging

### Goals

- Centralize logs with Promtail and Loki
- Build operational Grafana dashboards

### Deliverables

- `labs/lab06-centralized-logging.md`
- Dashboard JSON exports in `tooling/dashboards/`
- Structured ingestion configs in `tooling/configs/`

## Phase 4 - Detection

### Goals

- Build explainable anomaly detection on telemetry
- Detect beaconing-like periodicity and rare domains

### Deliverables

- `labs/lab07-anomaly-detection.md`
- Feature pipelines in `ml/features/`
- Models and scoring in `ml/models/`
- CLI reporting in `ml/analysis_cli/`

## Phase 5 - Defensive Engineering

### Goals

- Codify response playbooks
- Apply secure engineering and hardening practices

### Deliverables

- `docs/incident-response-playbooks.md`
- `docs/owasp-overview.md`
- Portfolio case studies in `portfolio/case-studies/`
