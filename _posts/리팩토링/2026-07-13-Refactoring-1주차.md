---
title: Refactoring Week 1
description: Refactoring
author: Cheongu Kim
date: 2026-07-13 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---


## 1. Review
Objective: Review the cybersecurity concepts learned at university.

### 1.1. Overall web service architecture
- Three-tier architecture: Front-end, Back-end, and Database. 
- Web servies operate based on the request-response model.

### 1.2. OSI 7-Layer Architecutre
The OSI model is the standard framework for network communication.

1. Application Layer
    - Provides network services directly to end-user applications.

2. Transport Layer
    - Provides reliable end-to-end communication through segmentation, error recovery, and flow control.

3. Network Layer
    - Determines routing paths and delivers packets between different networks.

4. Physical Layer
    - Transmits raw bits over physical media such as cables, fiber optics, and wireless signals.

### 1.3. Representitive Cyber Attack Methods
1. Distributed Denial of Service (DDoS)
    - Attackers flood the target server with massive amounts of traffic, exhausting its resources and making the service unavailable to legitimate users.

2. Injection Attack
    - Attackers inject malicious input into an application's input fields to execute unintended commands or manipulate the system.

3. Cross-Site Scripting (XSS)
    - Attackers inject malicious JavaScript into a trusted website.
    - The script executes when other users visit the compromised page, allowing attackers to steal cookies or session tokens.

4. Cross-Site Request Forgery (CSRF)
    - Attackers trick authenticated users into sending unintended requests to a trusted website without their knowledge.

5. Man-in-the-middle
    - Attackers intercept communication between two parties, allowing them to eavesdrop, modify, or steal sensitive information during data transmission.

## 2. Cybersecurity Industry Trends

### 2.1. Cybersecurity Job Roles
1. Security Operations Center (SOC) Analyst
    - Monitors security events, detects cyber threats, and responds to security incidents.

2. Penetration Tester (Ethical Hacker)
    - Simulates cyber attacks to identify vulnerabilities before malicious attackers can exploit them.

3. Security Consultant
    - Assesses organizational security posture and recommends security strategies, policies, and technical solutions.

4. Malware Analyst
    - Analyzes malicious software to understand its behavior, identify attack techniques, and develop detection methods.

### 2.2. Current Cybersecurity Trends
1. Zero-trust Architecture
    - Never trust, always verify.
    - Every user, device, and request must be authenticated and authorized.
    - Identity and Access Management (IAM)

2. AI-based Vulnerability Detection
    - AI assists in identifying software vulnerabilities, detecting abnormal behavior, and automating threat analysis.

## 3. Case Studies of Cybersecurity Incidents in South Korea

### 3.1. Coupang Personal Information Leak (June 2025)
Overview
- Personal information was leaked by a former employee.

Cause
- An authentication key that should have been revoked remained active.
- The attacker used the key to access customer information through external APIs.

Impact
- Personal information of more than 33 million customers was exposed.
- Approximately 150 million delivery address records were leaked.

### 3.2. Lotte Card Data Breach (August 2025)
Overview
- Customer information was compromised through an external cyber attack.

Cause
- Attackers exploited a vulnerability in the Oracle WebLogic Server, installed malware, and exfiltrated internal data.

Impact
- Personal information of more than 2 million customers was leaked.
- Approximately 200 GB of sensitive data was stolen.

### 3.3. Moduui Startup Data Leak (June 2026)
Overview
- Confidential personal information and startup proposals submitted by applicants were exposed.

Cause
- An AI solution provider participating in the project was compromised by a cyber attack, resulting in unauthorized access to applicant data.

Impact
- Personal information and business ideas of approximately 5,000 first-round applicants were leaked.

