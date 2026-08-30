---
title: Refactoring Week 8
description: Refactoring
author: Cheongu Kim
date: 2026-08-29 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---
# Virtual Environment
A virtual environment is an isolated environment that runs a Guest OS separately from the Host OS.

Virtual environment setup differs between financial and non-financial companies.
- Financial companies: An isolated analysis environment due to network segmentation requirements.
- Non-financial companies: No network segmentation restrictions; a virtual environment can be set up on the work PC.

## Virtual Environment Setup Guidelines

Malware analysis virtual environment: Configure the environment under the most vulnerable conditions to facilitate smooth analysis.

For tasks such as virtual environment setup, creating manuals such as an environment setup guide can be helpful for future handovers.

## Malware Sample Collection
Collecting malware samples for testing and analysis.
- In the past, it was difficult to obtain malware samples that actually executed malicious behavior.
- Today, various malware sample repositories are available, and new samples are continuously added. When using these sites, it is important to check whether they are actively maintained and regularly updated with new samples.

## Sample Sites
- MalwareBazaar
- Hybrid Analysis
- Malware Traffic Analysis
- Any.Run
- VirusShare