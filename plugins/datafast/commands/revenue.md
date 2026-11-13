---
description: Which sources and campaigns brought revenue (read-only)
---

Show which traffic sources and campaigns brought revenue. This is read-only. Range or site from the user: $ARGUMENTS

1. Call `list_sites` and pick the site.
2. Call `get_revenue` for the range (default: last 30 days) and `get_traffic_sources` for campaign detail.
3. Show totals per currency and a table of sources by revenue and visitors, with the date range.
4. If nothing is returned, say that no attributed revenue exists in the range or revenue is not connected; do not guess.
