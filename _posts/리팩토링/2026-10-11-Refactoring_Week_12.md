---
title: Refactoring Week 12
description: Refactoring
author: Cheongu Kim
date: 2026-10-11 22:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# Snort


- A practical tool for creating network detection signatures.
- Detection accuracy depends on proper Rule Header and Rule Option configuration.
- Use `any` in the Header and refine detection conditions in the Rule Body.
- Relying only on IP addresses and port numbers may cause false positives or false negatives.

---

## Rule Header

### General Configuration
- `any` is commonly used for IP addresses and port numbers.
- Specific IP and port configurations are used for targeted monitoring.

### Action
- `alert`, `log`, `pass`, `drop`, `sdrop`, `reject`
- `alert` is commonly used for generating detection events.

### Protocol, IP, Port
- TCP is commonly used.
- Use `any` unless specific IPs or ports are required.

### Direction
- `->` is generally preferred.
- Bidirectional rules (`<>`) may generate excessive events.
- Use bidirectional rules only when necessary.

---

## Rule Body (Rule Options)

### General
- Use keywords to define specific detection conditions.
- Prioritize essential options to avoid unnecessary complexity.

### Essential Keywords

**`msg`**
- Defines the alert message.
- Makes detection events easier to identify.

**`sid`**
- Assigns a unique ID to each detection signature.
- Start custom SIDs from `1000001`.

**`content`**
- Searches for specific strings or byte patterns.
- Identifies distinctive characteristics of malware traffic.

### Content Support Options
- `nocase`: Ignores letter case.
- `depth`: Limits the search depth.
- `offset`: Specifies the starting position of the search.

### `pcre`
- Uses regular expressions for pattern matching.
- Provides more flexible detection conditions.

### Additional Options
- `Non-Payload`: Inspects packet headers and connection states.
- `Post-Detection`: Defines actions or processing after a rule matches.
- Mainly used for more specialized detection scenarios.

---

## Key Takeaways
- Use the Rule Header to define basic traffic conditions.
- Use the Rule Body to identify distinctive network patterns.
- Prioritize `msg`, `sid`, and `content`.
- Use additional keywords to improve detection accuracy.