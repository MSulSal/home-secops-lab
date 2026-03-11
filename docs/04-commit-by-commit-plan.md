# Commit-by-Commit Plan

## Usage

Execute commits in order. Mark each as complete in `docs/06-delivery-ledger.md`.

## Sequence

| Unit | Commit Type | Commit Message | Objective | Files |
|---|---|---|---|---|
| C000 | `docs` | `docs: add terminal foundations and baseline runbook` | Establish operator onboarding and first baseline workflow | `README.md`, `docs/00-terminal-foundations.md`, `docs/01-node-baseline-and-attack-surface.md`, `labs/lab00-node-baseline.md`, `docs/templates/node-baseline-report-template.md` |
| C000A | `chore` | `chore: add repository ignore policy` | Keep private notes and runtime artifacts out of version control | `.gitignore` |
| C001 | `docs` | `docs: establish bootstrap and project plan` | Create stable resume entrypoint and phase plan | `BOOTSTRAP.md`, `PROJECT_PLAN.md` |
| C002 | `docs` | `docs: add layer mastery roadmap` | Define low-level to high-level mastery model | `docs/02-layered-mastery-roadmap.md` |
| C003 | `docs` | `docs: add attack surface visibility matrix` | Track surfaces, telemetry, and blind spots | `docs/03-attack-surface-and-visibility-matrix.md` |
| C003A | `docs` | `docs: add low-level systems track` | Define runtime, socket, and packet mastery objectives | `docs/05-low-level-systems-track.md` |
| C004 | `docs` | `docs: add commit execution plan and delivery ledger` | Make execution deterministic across context resets | `docs/04-commit-by-commit-plan.md`, `docs/06-delivery-ledger.md` |
| C005 | `docs` | `docs: add decision log and baseline report templates` | Preserve technical decisions and evidence format | `docs/07-decision-log.md`, `docs/templates/*` |
| C005A | `docs` | `docs: add documentation index` | Centralize doc navigation and source-of-truth links | `docs/README.md` |
| C006 | `feat` | `feat: add bootstrap script for host baseline capture` | Implement first operational Bash script | `tooling/scripts/bootstrap.sh` |
| C007 | `feat` | `feat: add node baseline parser and normalization script` | Convert raw command output to structured artifacts | `tooling/scripts/collect-node-baseline.sh` |
| C008 | `docs` | `docs: publish node baseline report v1` | Record first observed host posture | `docs/reports/node-baseline-001.md` |
| C009 | `feat` | `feat: scaffold docker compose for logging stack` | Introduce Loki/Promtail/Grafana baseline | `tooling/docker/docker-compose.yml`, configs |
| C010 | `feat` | `feat: add loki and promtail baseline configs` | Enable source labeling and ingestion | `tooling/configs/loki-config.yml`, `tooling/configs/promtail-config.yml` |
| C011 | `docs` | `docs: add logging pipeline validation runbook` | Define stack verification procedures | `labs/lab01-logging-pipeline-validation.md` |
| C012 | `feat` | `feat: add grafana provisioning baseline` | Standardize dashboards and datasource config | `tooling/dashboards/*`, provisioning configs |
| C013 | `feat` | `feat: add dns telemetry ingestion path` | Integrate DNS source data into pipeline | parser/config docs and scripts |
| C014 | `docs` | `docs: publish dns visibility investigation playbook` | Formalize DNS triage workflow | `docs/dns-visibility.md` |
| C015 | `feat` | `feat: add zeek sensor integration scaffold` | Add Zeek collection workflow | Zeek configs and ingestion mapping |
| C016 | `feat` | `feat: add suricata sensor integration scaffold` | Add Suricata event collection | Suricata configs and ingestion mapping |
| C017 | `docs` | `docs: publish nsm sensor placement and blind spot analysis` | Capture coverage limits and assumptions | `docs/network-monitoring.md` |
| C018 | `feat` | `feat: scaffold ml module structure and interfaces` | Create analyzable data flow contracts | `ml/*` scaffolding |
| C019 | `feat` | `feat: implement periodicity detector` | Detect beacon-like regular intervals | `ml/models/periodicity_*` |
| C020 | `feat` | `feat: implement ewma anomaly detector` | Detect deviations from baseline trend | `ml/models/ewma_*` |
| C021 | `feat` | `feat: implement isolation forest detector` | Multivariate outlier scoring | `ml/models/isolation_forest_*` |
| C022 | `feat` | `feat: add anomaly report cli` | Produce ranked human-readable findings | `ml/analysis_cli/*` |
| C023 | `docs` | `docs: publish anomaly analysis methodology` | Document detector rationale and limitations | `docs/anomaly-detection-methodology.md` |
| C024 | `docs` | `docs: add incident response playbooks` | Formalize containment and recovery workflows | `docs/incident-response-playbooks.md` |
| C025 | `chore` | `chore: add ci security and quality workflows` | Enforce reproducible checks and security scans | `.github/workflows/*`, hooks |

## Rules

- one objective per commit
- one reviewer-verifiable outcome per commit
- update delivery ledger immediately after each commit
