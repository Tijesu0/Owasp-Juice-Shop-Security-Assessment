# Owasp-Juice-Shop-Security-Assessment

## Project Overview
This project documents a security assessment of OWASP Juice Shop, an intentionally vulnerable web application designed for security testing and education.

The assessment focuses on identifying, investigating, reproducing and documenting web application vulnerabilities, with emphasis on authentication, authorization, input handling and application security controls.

## Assessment Objectives
- Examine the application's attack surface.
- Investigate authentication and authorization mechanisms.
- Investigate information disclosure vulnerabilities.
- Document vulnerabilities with supporting evidence.
- Evaluate security impact and recommend appropriate remediation measures.

## Tools
- Burp Suite
- Firefox

## Repository Structure
- (methodology)[https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/tree/main/methodology]: Testing approach and procedures.
- (findings)[https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/tree/main/findings]: Documented security vulnerabilities.
- (evidence)[https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/tree/main/evidence]: Supporting screenshots and other evidence for documented vulnerabilities.
- (final-report)[https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/tree/main/final-report]: Consolidated assessment report.

## Target Application
OWASP Juice Shop

## Assessment Status
Ongoing

## Assessment Methodology
Manual black-box web application security testing

## Disclaimer
Testing was performed against the intentionally vulnerable OWASP Juice Shop environment for educational and portfolio purposes.

## Findings
-[WEB-001-Unauthorized-Product-Review-Authorship](https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/blob/main/findings/WEB-001-Unauthorized-%20Product-Review-Authorship.md)

-[WEB-002-DOM-Based-Cross-Site-Scripting-in-Product-Search](https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/blob/main/findings/WEB-002-DOM-Based-Cross-Site-Scripting-in-Product-Search.md)

-[WEB-003-Unauthenticated-Access-to-Another-User's-Basket](https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/blob/main/findings/WEB-003-Unauthenticated-Access-to-Another-User's-Basket.md)

-[WEB-004-Account-Registration-and-Authentication-with-Empty-Credentials](https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/blob/main/findings/WEB-004-Account-Registration-and-Authentication-with-Empty-Credentials.md)

-[WEB-005-Authentication-Bypass-Through-Acceptance-of-Unsigned-JWT](https://github.com/Tijesu0/Owasp-Juice-Shop-Security-Assessment/blob/main/findings/WEB-005-Authention-Bypass-Through-Acceptance-of-Unsigned-JWT.md)
