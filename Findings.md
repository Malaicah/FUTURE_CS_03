# Detailed Findings - API Security Assessment

**Target:** https://api.restful-api.dev/  
**Assessment Date:** 2026-05-07  
**Assessor:** Nancy Cafti

---

## Critical Findings

### F-01: Missing Authentication on Write Operations (Critical)
**Description:** All write operations (POST, PUT, PATCH, DELETE) can be performed without any authentication. Anyone on the internet can create, modify, or delete data.

**Impact:** Complete data compromise possible (Data Poisoning & Destruction).

**Remediation:** Implement API key authentication or JWT/OAuth for all write endpoints.

---

### F-02: Unauthorized Data Manipulation (Critical)
**Description:** After creating an object, any user can modify or delete it using PATCH or DELETE. No ownership check exists.

**Impact:** No data ownership — attackers can tamper with or delete any object.

**Remediation:** Implement ownership tokens and user-scoped namespaces.

---

## High Risk Findings

### F-03: Predictable/Sequential Resource IDs
**Description:** Pre-seeded objects use sequential IDs, making full data enumeration easy.

**Remediation:** Implement pagination and cursor-based pagination.

### F-04: No Rate Limiting
**Description:** The API has no protection against abuse (DoS or scraping).

**Remediation:** Add rate limiting (e.g., 100 requests per minute per IP).

### F-05: Object ID Injection / Mass Assignment
**Description:** The API accepts dangerous fields in the request body.

**Remediation:** Use strict schema validation and DTOs.

---

## Medium Risk Findings

### F-07: Overly Permissive CORS Policy
**Description:** `Access-Control-Allow-Origin: *` allows any website to read API responses.

**Remediation:** Restrict to trusted domains only.

### F-08: Verbose Error Messages
**Description:** Error messages reveal internal logic and business rules.

**Remediation:** Return generic error messages only.

---

**Note:** All testing was performed ethically on a public demo API intended for learning purposes.
