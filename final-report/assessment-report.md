## Security 
OWASP Juice Shop - Security Assessment Report

## Target:
OWASP Juice Shop (Locally Hosted)

## Assessment Type: 
Manual Black-Box Web Application Security Assessment

## Assessment Period: 
November 2026

## Assessment Status: 
Ongoing 

## Executive Summary
A manual security assessment was conducted against OWASP Juice Shop to identify vulnerabilities affecting application security, authentication, authorization and 
input handling.

The assessment identified several security weaknesses, which are documented in the individual finding reports.

## Scope and Methodology
Testing focused on application functionality, API endpoints, authentication, authorization, input handling and business logic.

Burp Suite and a web browser were used to inspect application traffic, manipulate requests and investigate potential vulnerabilities.

Source-code review, infrastructure testing and automated vulnerability scanning were excluded.
Identified vulnerabilities were investigated to establish their reproducibility, security impact and appropriate measures


## Findings Summary

| ID | Vulnerability | Severity |
|---|---|---|
| WEB-001 | Unauthorized Product Review Authorship | Not Yet Assessed |
| WEB-002 | DOM-Based XSS | Not Yet Assessed |
| WEB-003 | Unauthorized Basket Access | Not Yet Assessed |
| WEB-004 | Empty Credential Registration and Authentication | Not Yet Assessed |
| WEB-005 | Authentication Bypass Through Unsigned JWTs | Not Yet Assessed |

## Conclusion
The assessment revealed weaknesses in several application security controls. Further testing is ongoing, and this report will be updated as additional findings are identified and validated.

