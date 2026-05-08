# FUTURE_CS_03 - API Security Assessment Report

## Task Overview
API Security Risk Analysis and Testing on a public RESTful API as part of Future Interns Cyber Security Track.

## Target API
- **Base URL**: https://api.restful-api.dev/
- **Type**: Public REST API with CRUD operations

## Tools Used
- **Postman** – API testing, collection management, and automation
- **Manual Testing** – Authentication bypass, authorization, rate limiting, and input validation

## Key Findings Summary

| Severity   | Count | Notable Issues |
|------------|-------|----------------|
| **Critical** | 2     | Missing Authentication on Write Operations, Unauthorized Data Manipulation |
| **High**     | 3     | Predictable Resource IDs, No Rate Limiting, Object ID Injection |
| **Medium**   | 2     | Overly Permissive CORS, Verbose Error Messages |

**Bottom Line:** The API allows anyone on the internet to create, modify, and delete data without any authentication — a critical security risk.

## Full Report
**[Download API Security Risk Analysis Report](./API_Security_Risk_Analysis_Report.pdf)**

## Detailed Findings
See [Findings.md](./Findings.md) for complete technical analysis and remediation steps.
