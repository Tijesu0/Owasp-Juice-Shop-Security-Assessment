## 1. Application Exploration
Initial reconnaissance was performed through manual interaction with OWASP Juice Shop application.
The application was explored in the same manner as a normal user would interact with it. This involved navigating through available pages and functionality to understand the application's structure, user workflows, and underlying business logic.

Particular attention was given to understanding:
1. Available application features and their intended functionality.
2. User actions and the workflows associated with those actions.
3. Business rules governing how application features operate.
4. Expected application behavior under normal usage conditions

This initial exploration provided an understanding of the application's functionality and helped establish potential areas for subsequent security testing.

## 2. HTTP Traffic Inspection
HTTP traffic inspection was performed during the investigation of individual application features.
Burp Suit Proxy was used to observe HTTP requests and responses generated when interacting with the application's functionality.
This allowed the examination of:
1. HTTP methods used by application endpoints.
2. Request URLs and API endpoint paths.
3. Request bodies and user supplied data.
4. Server responses to application requests.

The inspection helped establish how individual application features communicated with the server and provided the HTTP requests needed for subsequent manual security testing

## 3. API Endpoint Identification
API endpoints were identified by observing HTTP requests generated during normal interaction with the application.

Rather than relying o automated endpoint discovery tools or guessing paths, the assessment used application driven endpoint discovery.

When investigating individual features, the corresponding HTTP requests were examined to identify the endpoints responsible for handling those operations.

These endpoints subsequently served as entry points for manual security testing
