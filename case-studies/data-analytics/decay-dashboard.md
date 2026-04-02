---
layout: default
title: Case Study - SQL Powered Content Decay Dashboard
---
# Case Study: SQL Powered Content Decay Dashboard
## The Challenge
A large scale blog with 500+ articles was losing 10% of its total traffic month-over-month, but the team couldn’t identify which specific posts were failing until it was too late.

## The Zero Waste Solution
1. **Automated Decay Detection:** Built a BigQuery SQL workflow that automatically flags high-value URLs experiencing a >20% traffic drop.
2. **Resource Prioritization:** Developed a Looker Studio dashboard that ranks "at-risk" content by revenue potential, moving from manual audits to automated alerts.
3. **Historical Refresh Framework:** Pivoted editorial resources away from low-ROI new drafts toward high-ROI updates of existing assets, maximizing previous SEO investments.

## Tools Used
* BigQuery (SQL Data Warehousing)
* Looker Studio (Dashboarding & Viz)
* Search Console API
* Pandas (Python Data Library)

## The Business Impact
* **Traffic Recovery:** 35% lift in sessions for stale, high-value legacy content.
* **Resource Optimization:** 40% reduction in new content costs by prioritizing "Refresh" over "Rewrite."
* **Revenue Protection:** Reversed a 6-month downward trend on the site’s top 10 converting pages.

## The Deep Dive
* **Crawl Gap Analysis**
Utilized Google Search Console and, ScreamingFrog/SEMrush to identify the delta between URLs discovered and URLs indexed. This revealed that faceted navigation (dynamic filters for size, color, and price) were generating over 1.4M unique URL combinations that lacked business value.
* **Directive Optimization**
Implemented a global `Disallow` strategy within the robots.txt file to block search bots from crawling non-essential parameter strings. This immediately preserved the site's crawl budget for high priority product and category pages.
* **Canonical & Tag Consolidation**
Developed a logic based canonical tag framework to ensure that any filtered views that did get crawled would pass their link equity back to the root product page, preventing internal competition and duplicate content issues.
* **Validation & Monitoring**
Established a custom dashboard to monitor the indexation rate of new product launches. By reducing technical noise, we ensured that new inventory moved from "Discovered" to "Indexed" in an average of 3.2 days.