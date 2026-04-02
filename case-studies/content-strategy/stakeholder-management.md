---
layout: default
title: Case Study - Agency & Stakeholder Management
---
# Case Study: Agency & Stakeholder Management
## The Challenge
The company was over-paying an external agency for “low value” SEO tasks while internal technical debt continued to mount. Communication between the agency and the internal Dev team had completely broken down.

## The Zero Waste Solution
1. **Resource Rationalization:** Conducted an audit of external agency deliverables to separate high-value strategic work from "low-value" tasks that could be automated or brought in-house.
2. **Prioritization Logic (ICE):** Implemented an Impact, Confidence, and Ease (ICE) scoring system for technical tickets, ensuring the Dev team only focused on tasks with a clear revenue trajectory.
3. **The Translation Layer:** Acted as the primary liaison between technical departments and creative teams, translating complex crawl data into actionable, easy-to-understand executive summaries.

## Tools Used
* Jira / Asana (Project Management)
* ICE Scoring Framework (Prioritization)
* Looker Studio (Executive Summary Dashboards)
* Slack (Cross-Functional Communication)

## The Business Impact
* **Dev Alignment:** 90% completion rate on technical SEO tickets through improved requirement documentation.
* **Cost Efficiency:** Saved $5k/month by identifying and removing redundant agency "low-value" tasks.
* **Operational Flow:** Established a seamless SEO-to-Content-to-Dev pipeline, reducing project drag by 25%.

## The Deep Dive
* **Forensic URL Inventory**
I began by scraping the legacy subdomains to categorize 2,400+ URLs by traffic volume and backlink authority, ensuring no "high-equity" assets were left behind.

* **Regex Pattern Mapping**
Rather than manual entry, I engineered global Regex patterns to handle bulk directory shifts (e.g., migrating ```/blog/YYYY/MM/``` to a centralized ```/blog/structure```) while preserving the original slug integrity.
* **Automated Status Validation**
I developed a custom Python script using the ```requests``` library to simulate crawler behavior and verify that every legacy link triggered a clean 301 → 200 response sequence.
* **Latency & Chain Mitigation**
By auditing the server-side execution, I eliminated multi-hop redirect chains, ensuring link equity passed to the new destination in a single, millisecond-fast jump.