---
layout: default
title: Case Study - Multi-Touch Attribution Modeling
---
# Case Study: Multi-Touch Attribution Modeling
## The Challenge
A SaaS company was over investing in paid search because it appeared to be the primary driver of leads. However, the last-click model was ignoring the role of organic content in the early research phases of the 6-month sales cycle.

## The Zero Waste Solution
1. **Cross-Channel Stitching:** Integrated GA4 BigQuery exports with CRM data to track the full user journey from initial organic discovery to final conversion.
2. **Attribution Logic Overhaul:** Moved beyond "Last Click" reporting to a data-driven model that correctly attributes top-of-funnel educational content value.
3. **ROI Transparency:** Visualized the SEO-to-Revenue pipeline in a custom dashboard, providing stakeholders with clear evidence of organic search’s multi-touch impact.

## Tools Used
* GA4 Exploration Reports
* BigQuery SQL (User-Stitching)
* Google Tag Manager (Custom Event Tracking)
* Microsoft Excel (Statistical Modeling)

## The Business Impact
* **Transparency:** Identified that SEO assisted in 30% more conversions than "Last Click" reporting suggested.
* **Budget Alignment:** Shifted content spend toward top-of-funnel topics with the highest assisted conversion rate.
* **Executive Buy-in:** Secured a 20% increase in SEO budget by proving multi-touch ROI.

## The Deep Dive
* **Crawl Gap Analysis**
Utilized Google Search Console and, ScreamingFrog/SEMrush to identify the delta between URLs discovered and URLs indexed. This revealed that faceted navigation (dynamic filters for size, color, and price) were generating over 1.4M unique URL combinations that lacked business value.
* **Directive Optimization**
Implemented a global `Disallow` strategy within the robots.txt file to block search bots from crawling non-essential parameter strings. This immediately preserved the site's crawl budget for high priority product and category pages.
* **Canonical & Tag Consolidation**
Developed a logic based canonical tag framework to ensure that any filtered views that did get crawled would pass their link equity back to the root product page, preventing internal competition and duplicate content issues.
* **Validation & Monitoring**
Established a custom dashboard to monitor the indexation rate of new product launches. By reducing technical noise, we ensured that new inventory moved from "Discovered" to "Indexed" in an average of 3.2 days.