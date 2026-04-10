# GitHub Pulse Beta Launch Plan

**Owner:** Rachel Chen
**Launch Date:** December 2, 2025
**Duration:** 4 weeks (Dec 2 - Dec 30)

## Beta Cohort

12 engineering teams selected for diversity in size, org, and tooling maturity:

| Team | Org | Size | EM |
|------|-----|------|----|
| Platform Core | Platform | 12 | Sarah Kim |
| Auth and Identity | Platform | 8 | Jordan Lee |
| CodeQL Engine | Security | 9 | Chris Nakamura |
| Vulnerability Alerts | Security | 7 | David Okoye |
| Copilot Chat | Product | 11 | Lisa Huang |
| Actions Runtime | Product | 10 | Maria Santos |
| Data Platform | Data | 14 | Alex Chen |
| ML Infrastructure | Data | 8 | Tanya Morrison |
| Billing Core | Platform | 6 | Omar Farid |
| API Gateway | Platform | 9 | Priya Sharma |
| Secret Scanning | Security | 7 | Ben Torres |
| Projects Backend | Product | 10 | Nina Kovac |

Total: ~111 engineers, 12 EMs

## Success Criteria
- 8/12 teams actively using dashboard by week 2
- NPS > 40 by week 4
- Zero P0 bugs in production
- Weekly survey response rate > 50%

## Communication Plan
- Welcome email: Dec 2, 9am PT
- Slack channel: #github-pulse-beta (created)
- Office hours: Thursdays 2pm PT
- Feedback form: always-on in dashboard footer

## Rollback Plan
- Feature flag per-team: can disable individual teams
- Emergency switch: disable all beta access in under 5 minutes
- Data pipeline: can pause ingestion without data loss
