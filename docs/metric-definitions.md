# GitHub Pulse: Metric Definitions

**Author:** Rachel Chen
**Reviewed by:** Marcus Webb (Eng TL), Lin Zhang (Data)
**Status:** Final

## 1. Build Velocity

**Definition:** Pull requests merged per engineer per sprint (2-week rolling window)

**Data Source:** Pull Request API (merged_at, author)

**Calculation:**
- Count PRs merged in the 2-week window
- Divide by number of active engineers on the team
- Active = at least 1 commit or PR in the period
- Exclude bot-authored PRs (dependabot, renovate, github-actions)

**Display:** Trend line with 4-sprint rolling average. Sparkline on digest card.

## 2. Review Turnaround

**Definition:** Median time from review request to first substantive review submission

**Data Source:** Pull Request Review API (requested_reviewers, reviews)

**Calculation:**
- Start: review_requested event timestamp
- End: first review with status APPROVED, CHANGES_REQUESTED, or COMMENTED (with body > 10 chars)
- Exclude: self-reviews, bot reviews
- Weekend handling: configurable per-org (excluded by default)

**Display:** Distribution histogram with median line. P95 shown as secondary metric.

## 3. Deployment Confidence Score

**Definition:** Composite score (0-100) reflecting deployment reliability

**Components:**
- CI Pass Rate (40% weight): Percentage of workflow runs with conclusion "success" in last 30 days
- Rollback Frequency (30% weight): Deploys followed by reverts or hotfixes within 2 hours
- Deploy Cadence Regularity (30% weight): Consistency of deploy frequency vs team's own baseline

**Thresholds:**
- Green: 80-100 (healthy, ship with confidence)
- Yellow: 60-79 (some friction, worth investigating)
- Red: 0-59 (significant issues, recommend action)

**Data Source:** Actions API (workflow runs), Deployments API

## Anomaly Detection

All metrics include anomaly detection. An anomaly is flagged when:
- Metric moves > 2 standard deviations from 4-week rolling mean
- OR metric crosses a threshold boundary (e.g., deploy confidence drops from green to yellow)

Anomalies appear as callouts in the weekly digest and as banner alerts in the dashboard.
