# Beta Feedback Synthesis: Weeks 1-4

**Compiled by:** Rachel Chen
**Period:** December 2-30, 2025

## Participation Metrics
- 12 teams enrolled, 11 active (1 EM on parental leave)
- 47 survey responses across 4 weekly surveys (68% response rate)
- 23 messages in #github-pulse-beta Slack channel
- 3 office hours sessions, average 10 EMs per session

## Net Promoter Score Trajectory
| Week | NPS | Key Driver |
|------|-----|------------|
| 1 | 28 | Initial excitement tempered by data freshness issues |
| 2 | 38 | Data freshness fixed, trust building |
| 3 | 45 | 1:1 prep feature launched, immediate adoption |
| 4 | 52 | EMs reporting real time savings in 1:1 prep |

## What's Working

### Review Turnaround Visibility (9/11 teams)
Most impactful feature. Multiple EMs reported catching stuck PRs they would have missed.

> "I caught a PR that had been waiting for review for 4 days. The engineer hadn't said anything. Without Pulse, that would have been a week." - Sarah Kim

### Weekly Digest Format (7/11 teams)
Preferred over real-time dashboard for regular check-ins. EMs read it Monday morning.

### 1:1 Prep (5/11 teams, launched week 3)
Auto-generated talking points based on each report's recent activity. EMs report saving 15-20 minutes per report per week.

> "I used to spend Sunday evening writing 1:1 agendas. Now I just review what Pulse generates and add my own items." - Jordan Lee

## Top Feature Requests

1. **Slack integration for weekly digest** (8/11) - Currently email only
2. **Custom date ranges** (6/11) - Currently fixed periods only
3. **Export to PDF** (4/11) - For quarterly leadership reviews
4. **Mobile view** (3/11) - For checking on the go

## Bugs Resolved During Beta

| Bug | Severity | Resolution |
|-----|----------|------------|
| Data freshness lag (30+ min during peak) | P1 | Fixed in v0.4.2, moved to streaming pipeline |
| Wrong team attribution for multi-team engineers | P1 | Fixed in v0.4.3, added primary team designation |
| Digest sent at 3am PT instead of 9am | P2 | Timezone config corrected |

## Recommendation
Proceed to GA. Beta validates core value proposition. Prioritize Slack digest integration before GA launch.
