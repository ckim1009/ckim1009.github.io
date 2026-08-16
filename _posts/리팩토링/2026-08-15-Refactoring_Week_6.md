---
title: Refactoring Week 6
description: Refactoring
author: Cheongu Kim
date: 2026-08-15 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# VirusTotal

## 1. What is VirusTotal?
A website that provides analysis to determine whether given files or URLs are malicious. More than 70 security vendors evaluate the uploaded content.

## 2. Why it is widely used in Security Monitoring

When security events occur, a large number of domains and IP addresses are collected.
These domains and IP addresses need to be investigated immediately to determine whether they are malicious, since timely response is critical to effective incident handling.
VirusTotal is used to quickly investigate and verify suspicious files, URLs, domains, and IP addresses by leveraging multiple security vendors and threat intelligence sources.

## 3. Features

### 3.1. File
Analyze a file in two ways:
- Static Analysis: Analysis of the file
- Dynamic Analysis: Analysis of the file's behavior by executing it in a sandbox environment

### 3.2. URL
Analyze whether a URL is malicious by examining its detection results, domain information, HTTP responses, redirects, web content, and community reputation.

### 3.3. Search
Search for files, URLs, domains, and IP addresses to investigate their previous analysis results and relationships with other threat intelligence data.

## 4. Precautions
### 4.1. Exposure of Personal or Sensitive Information
Files containing personal, confidential, or sensitive information may be exposed when they are uploaded to VirusTotal. Therefore, sensitive files should be handled carefully before uploading them for analysis.

### 4.2. Reliability of Analysis Results
- VirusTotal analysis results should not be considered definitive evidence of whether a file or URL is malicious. 
- An `Undetected` result does not necessarily mean that the file or URL is safe, as false positives and false negatives are possible. 
- Sandbox analysis also has limitations, since some malware can detect sandbox environments and avoid executing malicious behavior within them.
