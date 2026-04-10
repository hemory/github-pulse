# Privacy Specification: GitHub Pulse

**Author:** Rachel Chen, with Privacy Engineering (Jamie Torres)
**Status:** Approved
**Review Date:** November 15, 2025

## Data Classification

### Team Aggregates (Low Sensitivity)
- Velocity, review turnaround, deploy confidence at team level
- Visible to: Team's EM, skip-level manager, org admins
- Minimum team size: 4 members (k-anonymity threshold)

### Individual Metrics (Medium Sensitivity)
- Same metrics but for a single contributor
- Visible to: ONLY the individual IC themselves
- Not visible to managers, peers, or org admins
- Purpose: Self-awareness and personal development

### Comparative Benchmarks (Low Sensitivity)
- Anonymized cross-team comparisons
- Opt-in per organization (disabled by default)
- No team names shown, only percentile ranges

## Privacy Controls

### Individual Opt-Out
- Any IC can opt out of all Pulse data collection
- Opt-out removes them from team aggregates retroactively
- Opt-out available in GitHub Settings > Pulse > Privacy
- Takes effect within 24 hours

### Data Retention
- Raw event data: 12 months
- After 12 months: aggregated to monthly summaries (no individual attribution)
- Aggregated data retained indefinitely for trend analysis
- Full deletion available upon request (GDPR/CCPA compliance)

### Access Logging
- All dashboard views are logged (who viewed what team, when)
- Quarterly access audit by Privacy Engineering
- Anomalous access patterns (e.g., viewing teams outside your org) trigger alert

## Compliance
- GDPR: Data Processing Agreement included in Enterprise ToS
- SOC 2: Pulse data covered under existing GitHub SOC 2 Type II
- CCPA: Deletion requests handled through existing privacy request flow
