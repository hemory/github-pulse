# GitHub Pulse 🫀

**Real-time team health dashboard for engineering managers.**

GitHub Pulse gives engineering managers a unified view of their team's delivery health — build velocity, review turnaround time, and deployment confidence — so they can spot friction early and celebrate momentum.

## Status

🟢 **GA Launch** — Rolling out to all GitHub Enterprise Cloud customers (March 2026)

## Features

- **Velocity Tracking** — Automated measurement of PRs merged, issues closed, and cycle time per sprint
- **Review Turnaround** — Real-time view of review request → approval latency with team and individual breakdowns  
- **Deployment Confidence Score** — Composite metric combining CI pass rate, rollback frequency, and deploy cadence
- **Team Comparison** — Anonymized benchmarks across similar-sized teams (opt-in)
- **Weekly Digest** — Automated Slack/email summary with trend arrows and anomaly callouts
- **Manager 1:1 Prep** — Auto-generated talking points based on each report's recent activity

## Architecture

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  Actions API │───▶│  Pulse Core  │───▶│  Dashboard  │
│  PR API      │    │  (Go service)│    │  (React)    │
│  Deploys API │    └──────────────┘    └─────────────┘
└─────────────┘           │
                    ┌─────▼──────┐
                    │  TimescaleDB│
                    └────────────┘
```

## Team

- **Product:** Rachel Chen (PM), Anika Patel (Design)
- **Engineering:** Marcus Webb (TL), Sofia Reyes, James Park, Dev Okonkwo
- **Data:** Lin Zhang

## Links

- [Product Spec](docs/PRD.md)
- [Beta Results](docs/beta-results.md)
- [Launch Readiness](docs/launch-readiness.md)
