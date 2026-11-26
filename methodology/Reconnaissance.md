## 1. Application Exploration
Initial reconnaissance was performed through manual interaction with OWASP Juice Shop application.
The application was explored in the same manner as a normal user would interact with it. This involved navigating through available pages and functionality to understand the application's structure, user workflows, and underlying business logic.

Particular attention was given to understanding:
1. Available application features and their intended functionality.
2. User actions and the workflows associated with those actions.
3. Business rules governing how application features operate.
4. Expected application behavior under normal usage conditions.

This initial exploration provided an understanding of the application's functionality and helped establish potential areas for subsequent security testing.

## 2. HTTP Traffic Inspection
HTTP traffic inspection was performed during the investigation of individual application features.
Burp Suite Proxy was used to observe HTTP requests and responses generated when interacting with the application's functionality.
This allowed the examination of:
1. HTTP methods used by application endpoints.
2. Request URLs and API endpoint paths.
3. Request bodies and user supplied data.
4. Server responses to application requests.

The inspection helped establish how individual application features communicated with the server and provided the HTTP requests needed for subsequent manual security testing.

## 3. API Endpoint Identification
API endpoints were identified by observing HTTP requests generated during normal interaction with the application.

Rather than relying on automated endpoint discovery tools or guessing paths, the assessment used application driven endpoint discovery.

When investigating individual features, the corresponding HTTP requests were examined to identify the endpoints responsible for handling those operations.

These endpoints subsequently served as entry points for manual security testing.


## 4. HTTP Request and Response Analysis
During reconnaissance, HTTP requests and responses were examined to understand the data exchanged between the browser and application server.
The examination included:
1. Request URLs and parameters: identifying endpoint paths and values supplied to application operations.
2. HTTP headers: Examining metadata and authentication related information included in reports.
3. Request bodies: inspecting data submitted to the application.
4. Identifiers: Observing references to users and other application resources.
5. Authentication data: Examining authentication related tokens and session information where present.
6. Server responses: Observing returned data, status codes and application behavior.

This analysis helped establish how application operations were structured and provided additional context for investigating potential security weaknesses.

## 5. Reconnaissance Summary
The reconnaissance phase established an understanding of the application's functionality, business logic, user workflows and HTTP communication.

Application features were explored manually while Burp Suite Proxy was used to identify API endpoints and examine the requests and responses associated with individual operations.

The information gathered during this phase provided the foundation for subsequent manual security testing.
