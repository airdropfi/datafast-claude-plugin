---
description: Short DataFast report for a site and date range (read-only)
---

Show a short DataFast report for the user's site. This is read-only. Range or site from the user: $ARGUMENTS

1. Call `list_sites` and pick the site (ask if several).
2. Call `get_traffic_summary`, `get_top_pages` and `get_traffic_sources` for the range (default: last 7 days).
3. Present visitors, pageviews, the top 5 pages and the top 5 sources with revenue where present, and state the date range used.
4. Report numbers exactly as returned. If revenue is empty, say revenue is not connected for that site.
