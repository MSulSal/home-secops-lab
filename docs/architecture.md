# Architecture

## Objective

Define the end-to-end defensive telemetry architecture and trust boundaries.

## Components

- DNS logging source (Pi-hole or AdGuard Home)
- Zeek telemetry sensor
- Suricata IDS sensor
- Promtail log shippers
- Loki log backend
- Grafana visualization and investigation
- `ml/` anomaly analysis module

## Data Flow

Document collection points, ingestion paths, retention strategy, and access controls.

## Trust Boundaries

Map management plane, monitored segments, and data-at-rest boundaries.

## Operational Notes

Capture scaling assumptions, backup strategy, and failure modes.
