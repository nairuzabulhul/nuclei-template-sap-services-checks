# SAP NetWeaver Service Detection

## Overview
This template is designed to detect the presence of various SAP services on SAP NetWeaver endpoints. It helps identify available SAP services and assess potential access control issues or redirection behaviors.

## Detection Criteria
This template uses multiple matchers and extractors to identify the status of each SAP service:

#### Status Codes Analyzed:
- **200 OK:** Service is available and responding.
- **301, 302, 303, 307, 308:** Redirects indicating possible access redirection.
- **403 Forbidden:** Indicates restricted access to the service.
- **404 Not Found:** The service endpoint does not exist on the server.
- **500+ Server Errors:** Indicates potential server misconfiguration.

## How to Run

### Prerequisites
- Ensure you have [Nuclei](https://github.com/projectdiscovery/nuclei) installed.
- Save the template file as `sap-netweaver-services-checks.yaml`.

### Basic Usage
```bash
nuclei -t sap-netweaver-services-checks.yaml -u https://target-url.com
