# API Specification: /team-health Endpoint

**Author:** Rachel Chen (PM), Marcus Webb (Eng TL)
**Version:** 1.0
**Status:** Implemented

## Endpoint

```
GET /api/v1/teams/{team_id}/health
```

### Authentication
Bearer token with `read:org` and `read:pulse` scopes.

### Parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| period | string | No | 30d | Time window: 7d, 14d, 30d, 90d |
| metrics | string | No | all | Comma-separated: velocity, review, deploy |
| include_anomalies | boolean | No | true | Include anomaly detection results |

### Response (200 OK)

```json
{
  "team_id": "platform-core",
  "team_name": "Platform Core",
  "period": {
    "start": "2025-11-01",
    "end": "2025-12-01"
  },
  "member_count": 12,
  "metrics": {
    "velocity": {
      "current": 5.2,
      "previous_period": 4.8,
      "trend": "up",
      "trend_pct": 8.3,
      "unit": "prs_per_engineer_per_sprint"
    },
    "review_turnaround": {
      "median_hours": 4.1,
      "previous_median_hours": 6.3,
      "trend": "improving",
      "p95_hours": 18.2
    },
    "deploy_confidence": {
      "score": 82,
      "trend": "stable",
      "components": {
        "ci_pass_rate": 0.94,
        "rollback_rate": 0.02,
        "deploy_regularity": 0.88
      }
    }
  },
  "anomalies": [
    {
      "metric": "review_turnaround",
      "severity": "warning",
      "detail": "p95 review time increased 40% week-over-week",
      "period": "2025-11-18/2025-11-25"
    }
  ]
}
```

### Error Responses

| Status | Description |
|--------|-------------|
| 403 | User lacks access to this team |
| 404 | Team not found |
| 422 | Invalid period or metric parameter |
| 429 | Rate limit exceeded (100 req/min per org) |

### Rate Limiting
100 requests per minute per organization. Rate limit headers included in response.
