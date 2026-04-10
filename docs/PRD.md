# GitHub Pulse: Product Requirements Document

**Author:** Rachel Chen, Senior Product Manager
**Last Updated:** October 15, 2025
**Status:** Approved

## Executive Summary

GitHub Pulse is a real-time team health dashboard for engineering managers. It provides unified visibility into build velocity, code review turnaround, and deployment confidence, replacing the manual data gathering that EMs currently do across multiple tools.

## Problem

Engineering managers spend 2-3 hours per week manually gathering delivery data for 1:1s and team health assessments. They lack visibility into review bottlenecks, have no trending data to spot regression, and cannot benchmark their team's cadence against historical performance.

## Solution

A dashboard integrated into the GitHub experience that automatically surfaces three core metrics:

1. **Build Velocity** - PRs merged per engineer per sprint, normalized for team size
2. **Review Turnaround** - Median time from review request to first substantive review
3. **Deployment Confidence** - Composite score combining CI pass rate, rollback frequency, and deploy cadence

## User Stories

### As an Engineering Manager, I want to...
- See my team's delivery trends at a glance so I can spot friction early
- Get a weekly digest of team health so I don't have to remember to check the dashboard
- Have auto-generated 1:1 talking points so my conversations are grounded in data
- Know when a team member's PR has been waiting for review for 48+ hours

### As a Director of Engineering, I want to...
- Compare delivery health across my org's teams (anonymized, opt-in)
- Understand which teams are trending down before it becomes a performance issue
- Export team health summaries for quarterly business reviews

## Success Metrics
- 60% weekly active usage among beta participants within 4 weeks
- Net Promoter Score > 40 from EM beta cohort
- 30% reduction in self-reported time spent preparing for 1:1s

## Privacy Principles
- Team-level aggregation by default (minimum 4 team members)
- Individual metrics visible only to the IC themselves
- Full opt-out available at individual level
- 12-month data retention, then aggregated to monthly summaries

## Rollout Plan
- Phase 1 (Oct-Nov): Core dashboard, velocity + review metrics
- Phase 2 (Dec-Jan): Deployment confidence, weekly digest
- Phase 3 (Feb-Mar): 1:1 prep, team comparison, GA launch
