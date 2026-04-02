---
layout: default
title: Case Study - The Leak Detection
---
# Case Study: The Leak Detection
## The Challenge
A B2B landing page was receiving high quality organic traffic, but the “Free Trial” sign-up rate was stagnating at 0.5%. The marketing team suspected the copy was the issue, but the data suggested a deeper technical friction point.

## The Zero Waste Solution
1. **Pathing Forensic Audit:** Analyzed GA4 behavioral flow data to identify specific landing pages where high-intent traffic was exiting the funnel.
2. **Friction Point Elimination:** Conducted heatmap and click-path analysis to identify UI/UX elements that were stalling the user journey.
3. **Strategic CTA Injection:** Optimized "Dead End" content with contextual calls-to-action, turning informational traffic into qualified marketing leads.

## Tools Used
* GA4 Path Explorations
* Hotjar (Heatmapping & Session Recording)
* Microsoft Clarity
* Google Tag Manager

## The Business Impact
* **Conversion Rate:** 22% increase in goal completions without increasing total traffic.
* **UX Efficiency:** Reduced funnel drop-off at the "Service Selection" stage by 15%.
* **Lead Quality:** 10% lift in MQLs (Marketing Qualified Leads) through CTA placement optimization.

## The Deep Dive
* **Crawl Gap Analysis**
Utilized Google Search Console and, ScreamingFrog/SEMrush to identify the delta between URLs discovered and URLs indexed. This revealed that faceted navigation (dynamic filters for size, color, and price) were generating over 1.4M unique URL combinations that lacked business value.
* **Directive Optimization**
Implemented a global `Disallow` strategy within the robots.txt file to block search bots from crawling non-essential parameter strings. This immediately preserved the site's crawl budget for high priority product and category pages.
* **Canonical & Tag Consolidation**
Developed a logic based canonical tag framework to ensure that any filtered views that did get crawled would pass their link equity back to the root product page, preventing internal competition and duplicate content issues.
* **Validation & Monitoring**
Established a custom dashboard to monitor the indexation rate of new product launches. By reducing technical noise, we ensured that new inventory moved from "Discovered" to "Indexed" in an average of 3.2 days.