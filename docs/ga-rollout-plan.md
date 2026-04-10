# GitHub Pulse: GA Rollout Plan

**Author:** Rachel Chen
**Effective:** March 10, 2026

## Rollout Schedule

| Wave | Date | Audience | Est. Orgs | Est. EMs |
|------|------|----------|-----------|----------|
| 1 | Mar 10 | Enterprise Cloud, 100+ engineers | 200 | 2,000 |
| 2 | Mar 17 | All Enterprise Cloud | 1,500 | 8,000 |
| 3 | Mar 24 | GitHub Team plan | 5,000 | 15,000 |

## Go/No-Go Criteria Between Waves
- Error rate < 0.1%
- No P0 bugs
- Support ticket volume < 50/week
- No data accuracy complaints

## Communications

### External
- **Blog post:** "Introducing GitHub Pulse" (scheduled Mar 10, 9am PT)
- **Changelog:** Feature announcement with screenshots and demo GIF
- **Email to Enterprise admins:** 1 week before their wave, opt-in instructions
- **Social:** Twitter/LinkedIn from @github account, Mar 10

### Internal
- **All-hands:** Demo slot Mar 11 (Rachel presenting)
- **Eng all-hands:** Architecture deep dive Mar 13 (Marcus presenting)
- **#ship-it Slack:** Announcement with metrics and team recognition

## Success Metrics (30 days post-GA)
- 20% activation rate among eligible orgs
- 50% WAU among activated orgs
- NPS > 40
- < 5 P1 bugs
- Support tickets < 50/week

## Emergency Procedures
- Feature flag allows per-org disable within 1 minute
- Full product disable: feature flag flip, < 5 minutes
- Data pipeline pause: does not affect existing dashboard data, just stops updates
- Rollback to pre-Pulse: remove feature flag, dashboard returns 404
