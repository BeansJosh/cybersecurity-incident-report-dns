# Network Traffic Analysis: DNS & ICMP Incident Report

## Overview
This repository contains a cybersecurity incident report analyzing DNS and ICMP traffic from a simulated network issue. The exercise involved investigating why users were unable to access a website and received a “destination port unreachable” error. This is part of my Google CyberSecurity Professional Certification course.

## Scenario Summary
Several customers reported they could not reach the website **www.yummyrecipesforme.com**. When attempting to load the page, the browser returned a “destination port unreachable” error. 

A packet capture (tcpdump) was taken while reproducing the issue. The capture showed repeated DNS queries being sent to a DNS server, followed by ICMP “port unreachable” responses.

## Key Findings
- The client sent UDP DNS queries (port 53) requesting the A record for the domain.
- The DNS server responded with **ICMP destination unreachable (port 53 unreachable)**.
- This indicates the DNS server was not listening on port 53 (DNS service was down, misconfigured, or blocked).
- As a result, name resolution failed and the website could not be reached.

## Contents
- `filled-incident-report.pdf` - Completed incident report following the provided template
- `template-blank.pdf` - Original blank template (for reference)

## Tools Used
- tcpdump (network protocol analyzer)
- Analysis of UDP and ICMP traffic

## Outcome
The root cause was identified as the DNS server not accepting traffic on port 53. This prevented successful DNS resolution for the target domain.
