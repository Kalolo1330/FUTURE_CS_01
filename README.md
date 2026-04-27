FUTURE_CS_01 – Vulnerability Assessment Report

Cyber Security Track
Future Interns Internship (2026)
Task 1: Vulnerability Assessment Report for a Live Website (Read-Only Scope)

📋 Project Overview

This repository contains the deliverables for Cyber Security Task 1 assigned by Future Interns.

The task involved performing a read-only vulnerability assessment on a publicly available practice website in order to identify common security weaknesses and document them in a professional report format.

The assessment was conducted using passive reconnaissance techniques, meaning no exploitation or intrusive attacks were performed.

 Target Website
Application: demo.testfire.net
IP Address: 65.61.137.117
Purpose: Publicly available vulnerable banking application used for security testing and education
 Tools Used
1️⃣ Nmap

Used for basic port scanning and service detection.

Example command used:

nmap -sV -Pn demo.testfire.net

Purpose:

Identify open ports
Detect running services
Gather service version information
2️⃣ WhatWeb

Used to detect the technology stack and server configuration of the target website.

Example command:

whatweb -v demo.testfire.net

Detected technologies:

Apache server
Apache-Coyote/1.1
Java backend
JSESSIONID cookies
HttpOnly cookie flag

Evidence saved as:

evidence/whatweb.txt
evidence/whatweb.png
3️⃣SYNK Security Headers Scanner

Used to analyze HTTP security headers of the web application.

Key results identified missing security headers such as:

Content-Security-Policy
X-Frame-Options
X-Content-Type-Options
Referrer-Policy
Permissions-Policy

The scan also detected:

Website served over HTTP
Server information disclosure
📄 Deliverables Included
Vulnerability_Assessment_Report.pdf
README.md
evidence/

Evidence folder contains:

whatweb.txt
whatweb.png
nmap_scan.txt
security_headers_report.txt

These files document the findings gathered during the assessment.

KEY FINDINGS SUMMARY
Missing Security Headers

Several recommended HTTP security headers were not configured:

Content-Security-Policy
X-Frame-Options
X-Content-Type-Options
Referrer-Policy
Permissions-Policy

These headers help protect websites against:

Cross-Site Scripting (XSS)
Clickjacking attacks
MIME-type sniffing
Information leakage
Server Information Disclosure

The server exposes detailed version information:

Server: Apache-Coyote/1.1

This may allow attackers to identify potential vulnerabilities related to the server software.

Cookie Security Weakness

The application uses a session cookie:

JSESSIONID

While it includes the HttpOnly flag, it lacks the SameSite attribute, which may increase risk of Cross-Site Request Forgery (CSRF) attacks.

⚠️ Overall Risk Level

Low – Medium

The vulnerabilities discovered mainly involve misconfigurations and information disclosure, which could assist attackers during reconnaissance phases.

📌 Scope & Methodology

Allowed activities:

Passive reconnaissance
Header inspection
Technology fingerprinting
Service identification

Not performed:

Exploitation
SQL Injection testing
Brute force attacks
Directory brute forcing
Denial-of-Service attacks

All testing was conducted in read-only mode, respecting ethical guidelines.

🚀 How to View the Report
Download Vulnerability_Assessment_Report.pdf
Review the evidence/ folder for supporting scans
Check screenshots and tool outputs used to identify vulnerabilities
📚 References
OWASP Web Security Testing Guide
Sample vulnerability reports from GitHub (as suggested in the task)

PROJECT STRUCTURE
<img width="573" height="264" alt="image" src="https://github.com/user-attachments/assets/dc6abd8c-1c64-443e-a51e-6a374f0a307c" />

