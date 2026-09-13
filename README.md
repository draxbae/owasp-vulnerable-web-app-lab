# OWASP Vulnerable Web App Lab

Hands-on web security assessment lab using OWASP Juice Shop in a local, isolated environment.

## Lab Overview

This project documents practical web security testing against OWASP Juice Shop, a deliberately vulnerable web application designed for security training.

The lab was deployed locally using Docker and assessed from Kali Linux.

## Objectives

- Practice web application security assessment
- Identify common OWASP web vulnerabilities
- Understand vulnerability impact and security risks
- Collect evidence from controlled laboratory testing
- Document findings using a professional security assessment format

## Lab Environment

| Component | Details |
|---|---|
| Target Application | OWASP Juice Shop |
| Deployment | Docker |
| Testing Platform | Kali Linux |
| Environment | Local / Isolated Lab |
| Application Port | 3000 |

## Methodology

### 1. Lab Deployment

Deployed OWASP Juice Shop locally using Docker and verified that the application was accessible.

### 2. Application Reconnaissance

Reviewed the application's available functionality and security challenge categories.

### 3. Vulnerability Testing

Performed controlled testing against selected Juice Shop challenges.

### 4. Evidence Collection

Captured screenshots showing the application's behavior and successful challenge results.

### 5. Documentation

Documented the findings, impact, evidence, and recommended security improvements.

## Findings

### 1. DOM-Based Cross-Site Scripting (DOM XSS)

**Severity:** Medium

A crafted input caused JavaScript execution in the browser, demonstrating a DOM-based cross-site scripting condition.

**Impact:**

Depending on the application context, DOM XSS can allow attacker-controlled JavaScript to execute in a victim's browser and potentially affect user actions or application data.

**Evidence:**

See `screenshots/dom-xss.png`.

**Recommended Mitigation:**

- Avoid unsafe DOM manipulation with untrusted input
- Properly validate and sanitize user-controlled data
- Use contextual output encoding
- Implement Content Security Policy as defense-in-depth

---

### 2. Confidential Document Exposure

**Severity:** Medium

A confidential document was accessible through the application's exposed file directory.

**Impact:**

Unauthorized access to confidential documents can expose sensitive business information and potentially affect confidentiality.

**Evidence:**

See `screenshots/confidential-document.png`.

**Recommended Mitigation:**

- Restrict access to sensitive files
- Do not store confidential documents in publicly accessible directories
- Apply proper authorization controls
- Review web server file exposure and directory configuration

---

### 3. Error Handling / Stack Trace Information Disclosure

**Severity:** Low

An unexpected request generated a detailed server-side error response containing application paths, framework information, and a stack trace.

**Impact:**

Detailed error messages can disclose internal application architecture and implementation details that may assist further attacks.

**Evidence:**

See `screenshots/error-handling.png`.

**Recommended Mitigation:**

- Disable detailed error messages in production
- Return generic error responses to users
- Log detailed errors server-side
- Implement centralized error handling

## Tools Used

- Kali Linux
- Docker
- OWASP Juice Shop
- Web Browser

## Key Learning Outcomes

- Web application security testing
- DOM XSS identification
- Sensitive information exposure analysis
- Error handling assessment
- Security evidence collection
- Vulnerability documentation
- OWASP-based security assessment methodology

## Security Notes

This project was performed entirely within a local, intentionally vulnerable laboratory environment.

No real-world systems, accounts, or unauthorized infrastructure were targeted.

Sensitive challenge data, credentials, and detailed exploitation procedures are intentionally excluded from this repository.

## Project Status

### Completed

- [x] OWASP Juice Shop deployment
- [x] Local security testing environment
- [x] DOM XSS challenge
- [x] Confidential Documents challenge
- [x] Error Handling challenge
- [x] Evidence collection
- [x] Security finding documentation

## Disclaimer

This repository is an educational project demonstrating web application security assessment techniques in an authorized laboratory environment.
