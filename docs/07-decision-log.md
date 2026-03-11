# Decision Log

## Purpose

Record architectural and operational decisions with explicit rationale and consequences.

## Entry Format

| ID | Date | Decision | Rationale | Alternatives Considered | Consequence |
|---|---|---|---|---|---|
| D-0001 | 2026-03-11 | Start in Kali WSL with host-node first visibility | Fast iteration and controlled baseline collection | Full-network sensor first | Early velocity with known visibility limits |
| D-0002 | 2026-03-11 | Bash-only automation scripts | Cross-platform shell consistency in Linux-first environment | PowerShell scripts | Lower friction in Kali and containers |

## Rules

- each non-trivial architecture choice gets an entry
- if a decision is reversed, add a new entry instead of editing history
- decisions must include operational consequence
