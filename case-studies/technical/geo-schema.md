---
layout: default
title: Case Study - GEO & Schema
---

# Case Study: GEO & Schema
## The Challenge
A B2B SaaS provider wanted to move beyond tradition blue ink rankings and secure “primary answer” status within AI-driven search environments (Google SGE, Gemini, and ChatGPT). The existing site lacked a machinereadable data layer, making it difficult for LLMs to accurately cite the brand’s specific services and expertise.

## The Zero Waste Solution
1. **Entity Relationship Mapping:** Conducted a gap analysis between site entities and the Google Knowledge Graph to identify missing semantic connections.
2. **Nested Schema Architecture:** Implemented advanced JSON-LD nesting (Organization > Product > Review) to provide explicit context for LLM crawlers and Answer Engines.
3. **Machine-Readable Layering:** Optimized site-wide microdata to ensure search bots can extract mission-critical facts without relying on heavy text-parsing resources.

## Tools Used
* JSON-LD Generator (Custom Schema Nesting)
* Classy Schema (Visualization & Validation)
* Google Rich Results Test
* Schema.org Vocabulary

## The Business Impact
* **AI Visibility:** 25% increase in "Cite-ability" within AI-overviews and SGE results.
* **Rich Snippets:** Secured 4 new "Service" and "Product" rich result types on Page 1.
* **CTR Lift:** 12% increase in Click-Through Rate on high-priority transactional queries.

## The Deep Dive
* **Crawl Gap Analysis**
Utilized Google Search Console and, ScreamingFrog/SEMrush to identify the delta between URLs discovered and URLs indexed. This revealed that faceted navigation (dynamic filters for size, color, and price) were generating over 1.4M unique URL combinations that lacked business value.
* **Directive Optimization**
Implemented a global `Disallow` strategy within the robots.txt file to block search bots from crawling non-essential parameter strings. This immediately preserved the site's crawl budget for high priority product and category pages.
* **Canonical & Tag Consolidation**
Developed a logic based canonical tag framework to ensure that any filtered views that did get crawled would pass their link equity back to the root product page, preventing internal competition and duplicate content issues.
* **Validation & Monitoring**
Established a custom dashboard to monitor the indexation rate of new product launches. By reducing technical noise, we ensured that new inventory moved from "Discovered" to "Indexed" in an average of 3.2 days.