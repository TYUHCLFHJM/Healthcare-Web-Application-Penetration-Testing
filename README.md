# Healthcare Web Application Penetration Testing

![Status](https://img.shields.io/badge/Status-Assessment%20documented-blue) ![Environment](https://img.shields.io/badge/Environment-Educational-green) ![Tools](https://img.shields.io/badge/Tools-Burp%20Suite%20%7C%20ZAP-orange)

## Executive summary

I conducted the documented reconnaissance and web security assessment stages of a black-box healthcare application exercise using Kali Linux, Burp Suite Community Edition and OWASP ZAP. The supplied evidence shows HTTP traffic inspection, authentication interface review and ten scanner alert categories. No successful authentication bypass, confidential document retrieval, password recovery or confidential business data exposure is established by the supplied screenshots. Overall application risk remains undetermined pending validation.

## Scope and rules of engagement

The training brief describes a five-day authorized educational engagement limited to the designated application, excluding denial of service, social engineering and out-of-scope testing. This portfolio is anonymized because the brief is marked confidential. Authorization to test is not authorization to publish; obtain instructor approval before public release.

## Tools and methodology

| Tool | Documented use |
|---|---|
| Kali Linux | Environment preparation and evidence organization |
| Browser developer tools | HTML and storage inspection |
| Burp Suite Community Edition | Proxy setup and HTTP request/response review |
| OWASP ZAP | Manual exploration and scanner alert review |
| John, Johnny, ExifTool, Poppler, qpdf, curl | Installation requested; subsequent use not demonstrated |

The workflow consisted of environment preparation, application navigation, browser inspection, HTTP traffic review and scanner alert triage. No active exploitation is established by the supplied evidence.

## Findings and risk ratings

ZAP displayed 0 high, 3 medium, 5 low and 2 informational alert categories. These are scanner classifications, not independently verified exploitability or CVSS scores.

| Finding | Provisional rating | Interpretation | Recommended remediation |
|---|---|---|---|
| Anti-CSRF tokens not detected | Medium | Scanner observation; exploitability depends on state-changing actions and other protections. | Use server-validated anti-CSRF tokens and origin checks. |
| Content Security Policy not detected | Medium | Missing defense-in-depth against script injection; no XSS demonstrated. | Deploy a restrictive CSP and test compatibility. |
| Anti-clickjacking header not detected | Medium | Potential framing risk; no successful clickjacking demonstrated. | Use CSP frame-ancestors and appropriate X-Frame-Options. |
| HttpOnly cookie attribute absent | Low | Observed cookie configuration; script access risk depends on context. | Set HttpOnly for session cookies. |
| SameSite cookie attribute absent | Low | Explicit cross-site cookie policy not observed. | Set an appropriate SameSite policy. |
| Technology disclosure in response headers | Low | Technology information was visible; no vulnerable version established. | Suppress unnecessary technology banners and maintain patching. |
| HSTS header not detected | Low | Scanner reports missing transport policy; no downgrade demonstrated. | Enable HSTS after validating HTTPS deployment. |
| X-Content-Type-Options not detected | Low | Missing MIME-sniffing protection. | Set X-Content-Type-Options: nosniff. |
| Cache-control review | Informational | Requires review of sensitive response caching; exposure not established. | Use no-store for sensitive responses where appropriate. |
| Session management response identified | Informational | Session handling observed; not itself a vulnerability. | Review session rotation, expiration and invalidation. |

## Milestone status

| Milestone | Evidence status |
|---|---|
| M1 — Initial access | Reconnaissance documented; restricted access and three PDFs not demonstrated |
| M2 — File security assessment | Not demonstrated |
| M3 — Confidential data exposure | Not demonstrated |
| M4 — Reporting | Report prepared for the documented assessment only |

## Evidence gallery

The following images are sanitized derivatives of the 22 supplied screenshots. Some panels are deliberately withheld rather than publishing target-specific traffic, identifiers or confidential material. Original evidence should remain in the private instructor submission.

### 01. Package index update

![Package index update](./screenshots/01.png)

### 02. IPv4 package index update

![IPv4 package index update](./screenshots/02.png)

### 03. Security tool installation request

![Security tool installation request](./screenshots/03.png)

### 04. Project directory creation

![Project directory creation](./screenshots/04.png)

### 05. Project directory navigation

![Project directory navigation](./screenshots/05.png)

### 06. Evidence folder creation

![Evidence folder creation](./screenshots/06.png)

### 07. Evidence folder verification

![Evidence folder verification](./screenshots/07.png)

### 08. Application homepage

![Application homepage](./screenshots/08.png)

### 09. HTML inspection

![HTML inspection](./screenshots/09.png)

### 10. Browser storage inspection

![Browser storage inspection](./screenshots/10.png)

### 11. Burp configuration

![Burp configuration](./screenshots/11.png)

### 12. Burp proxy initialization

![Burp proxy initialization](./screenshots/12.png)

### 13. Browser navigation

![Browser navigation](./screenshots/13.png)

### 14. HTTP history

![HTTP history](./screenshots/14.png)

### 15. HTTP request inspection

![HTTP request inspection](./screenshots/15.png)

### 16. HTTP response inspection

![HTTP response inspection](./screenshots/16.png)

### 17. Staff response inspection

![Staff response inspection](./screenshots/17.png)

### 18. Patient response inspection

![Patient response inspection](./screenshots/18.png)

### 19. Staff authentication interface

![Staff authentication interface](./screenshots/19.png)

### 20. Patient authentication interface

![Patient authentication interface](./screenshots/20.png)

### 21. ZAP initialization

![ZAP initialization](./screenshots/21.png)

### 22. ZAP alert overview

![ZAP alert overview](./screenshots/22.png)

## Conclusion

The exercise demonstrates security tooling preparation, web traffic interpretation, scanner triage and remediation planning. The observed alerts provide a basis for defensive hardening, but do not establish successful exploitation. Further authorized validation and evidence are needed to complete the remaining milestones.

## Additional documentation

- [Detailed assessment report](reports/penetration-testing-report.md)
- [Publication and evidence handling](reports/evidence-handling.md)
