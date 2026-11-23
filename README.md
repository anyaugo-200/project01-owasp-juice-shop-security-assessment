# Project 01 - OWASP Juice Shop Web Application Security Assessment

## Overview

This project is a public portfolio demonstration of a web application and API security assessment against OWASP Juice Shop, an intentionally vulnerable training application. The work demonstrates how to document findings with evidence, explain business impact, map issues to OWASP guidance, and provide remediation and retest steps.

**Evidence report:** [project-01-owasp-juice-shop-security-assessment.pdf](project-01-owasp-juice-shop-security-assessment.pdf)

> **Related:** This is the concise, client-style findings report. For the full end-to-end methodology on the same practice target — attacker-style recon, attack-surface mapping, and the lab built as code — see **[project05 — Web Application Exposure Review](https://github.com/anyaugo-200/project05-web-application-exposure-review)**.


## Scope

- Target: OWASP Juice Shop running locally at `http://localhost:3000`
- Environment: isolated local lab
- Assessment type: web application and API security assessment
- Methodology: OWASP Web Security Testing Guide v4.2 and OWASP Top 10:2025
- Classification: public portfolio sample / non-client demonstration

## Findings Demonstrated

| ID | Finding | Severity in report | What was demonstrated |
| --- | --- | --- | --- |
| 1 | SQL Injection - Authentication Bypass | Critical | A controlled injection test against the login flow resulted in successful lab authentication and token evidence. |
| 2 | Sensitive Data Exposure via Directory Listing | High | The public `/ftp` endpoint exposed directory contents and an internal document in the lab. |
| 3 | DOM-Based Cross-Site Scripting | High | Search input was reflected into the DOM and executed controlled JavaScript in the lab origin. |
| 4 | Information Disclosure via Exposed API Documentation | Medium | Swagger/OpenAPI documentation was reachable at `/api-docs` without authentication in the lab. |
| 5 | Insecure Direct Object Reference on User Baskets | High | A request to `/rest/basket/{id}` returned another user's basket data in the lab context. |

## Tools And Techniques

- OWASP Juice Shop
- Chrome Developer Tools
- Manual browser testing
- XHR/fetch inspection
- Browser storage inspection
- Screenshot evidence collection
- OWASP WSTG-style reporting

## Skills Demonstrated

- Web application vulnerability analysis
- Authentication and authorization testing
- API request/response inspection
- Evidence capture and finding write-up
- Business impact explanation
- Remediation and retest planning

## Retest Plan

Each finding is documented with evidence, business impact, a **recommended fix and a retest plan** — covering rechecking the authentication bypass, blocking public directory access, confirming XSS payloads render safely as text, restricting API documentation, and enforcing object-level authorization checks.

No fix was applied and no retest was performed in this project: OWASP Juice Shop is intentionally vulnerable and cannot be patched. The above is the plan a real engagement would run to confirm a client's remediation — not a record of a completed retest.

## Boundary

This is a lab report against an intentionally vulnerable application. It is not an assessment of a real company system and should not be interpreted as evidence of risk in any third-party environment.
