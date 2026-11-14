## 1.Assessment Overview
This project documents a web application security assessment conducted against OWASP Juice Shop, an intentionally vulnerable web application designed for security training and testing.

This assessment involves examining application functionality, investigating security weaknesses, reproducing vulnerabilities and documenting findings with supporting evidence.

## Target Application: 
   Owasp Juice Shop

## Assessment Environment:
Locally hosted instance

## Assessment Type: 
Web Application Penetration Testing

## Testing Approach:
Manual Security Testing

## Assessment Period:
November 2026

## Tester:
Tijesu0

## 2.Assessment Objectives
The objectives of this assessment were to:
1. Examine the application functionality and identify potential attack surface.
2. Evaluate authentication mechanisms and JWT handling
3. Assess access-control enforcement and identify unauthenticated access possibilities
4. Investigate input-handling weaknesses, including SQL injection and cross-site scripting
5. Document identified vulnerabilities, demonstrate their impact and recommend remediation measures

## 3.Scope
The assessment focused on the OWASP Juice Shop web application, including its browser-accessible functionality and API endpoints.
The following areas were included:
1. Web Application Functionality: Examination of application pages, features and user workflows.
2. API Endpoints: Inspection and manual testing of API requests and responses using Burp Suit.
3. Authentication and Token Handling: Examining of authentication mechanisms and JWT-related behavior.
4. Access Control: Assessment of authorization enforcement, user permissions and access restrictions.
5. Input Handling: Investigation of user controlled input and potential injection vulnerabilities

## 4.Out of Scope Activities
The following activities were excluded from this assessment:
1. Source code review and white box testing.
2. Infrastructure and operating system penetration testing.
3. Denial of service and stress testing
4. Social engineering testing.
5. Attacks against external systems or unrelated third party services.

## 5. Testing Approach
The assessment was conducted using a manual black-box testing approach.
Testing involved interacting with application's browser accessible functionality and examining HTTP communication between the browser and the application.
Burp Suit was used to support HTTP traffic inspection and manipulation through the following components:
1. Proxy: Used to intercept and inspect HTTP requests and responses generated during application interactions.
2. Repeater: Used to modify and resend HTTP requests to examine server-side behavior under different input conditions.

Testing focused on identifying weaknesses in authentication, token handling, access control and input processing.
Identified vulnerabilities were investigated and documented with supporting evidence.

## 6. Assessment Limitations
The assessment was conducted manually without automated vulnerability scanning tools.
The following limitations applied:
1. No automated vulnerability scanning was performed using Burp Suit Scanner.
2. Source code review was not conducted.
3. Infrastructure level security testing was not performed
4. Testing was limited to the application functionality and endpoints examined during the assessment.
5. Findings should not be interpreted as evidence that all application vulnerabilities have been identified.  
