---
name: google-ads
description: Use when querying or analysing Google Ads data — campaigns, keywords, spend, performance. Covers connection method, GAQL query patterns, and mutation safety rules.
---

# Google Ads — Access & Query Guide

## First-Run Setup

Before using this skill, you need:
1. A Google Ads API developer token
2. A service account JSON file with Google Ads API access
3. A `google-ads.yaml` config file

Set these paths in your environment or tell Claude where they are on first use.

## How to Query

Prefer the **MCP tool** (`google-ads`) when available.

Fallback: run a Python script:

```python
from google.ads.googleads.client import GoogleAdsClient

client = GoogleAdsClient.load_from_storage("path/to/google-ads.yaml")
ga_service = client.get_service("GoogleAdsService")

query = """
    SELECT <fields>
    FROM <resource>
    WHERE <conditions>
    LIMIT 100
"""

response = ga_service.search(customer_id="YOUR_CUSTOMER_ID", query=query)
for row in response:
    print(row)
```

## GAQL Patterns

```sql
-- Active campaigns with spend
SELECT campaign.id, campaign.name, campaign.status,
       metrics.cost_micros, metrics.clicks, metrics.impressions
FROM campaign
WHERE campaign.status = 'ENABLED'
  AND segments.date DURING LAST_30_DAYS

-- Keywords
SELECT ad_group_criterion.keyword.text,
       ad_group_criterion.keyword.match_type,
       metrics.cost_micros, metrics.clicks
FROM keyword_view
WHERE campaign.status = 'ENABLED'
  AND segments.date DURING LAST_7_DAYS

-- Search terms
SELECT search_term_view.search_term, metrics.clicks, metrics.cost_micros
FROM search_term_view
WHERE segments.date DURING LAST_7_DAYS
```

- `cost_micros` = cost in micros (divide by 1,000,000 for your currency)
- Use `segments.date DURING LAST_7_DAYS / LAST_30_DAYS` for date ranges
- Filter by `campaign.status = 'ENABLED'` to exclude removed/paused

## Mutations — Strict Safety Rule

**Never apply mutations** (bid changes, budget changes, pause/enable) unless the user gives the explicit directive:

> "google ads commit"

Until that directive: describe what would change, show the mutation code, and wait for confirmation.
