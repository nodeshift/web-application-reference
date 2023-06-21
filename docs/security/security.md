# Security

## Overview
Security is strongest from conscious design at the outset, rather than retroactively trying to fill gaps after a solution has been built. In this respect, security should be considered at every stage of the applications lifecycle.

A [threat model](https://www.ibm.com/garage/method/practices/code/threat-modeling/) should be considered based on the attack surface that the Web Application creates. A public-facing web application for highly confidential personal data will have a very different threat model to an internal web application that doesn't contain sensitive data nor control anything of value.

This section focuses on some of the common security threats to defend against and mitigation techniques to utilise from the `team`'s experience building web applications.

---

## Guidance

The consensus of the most critical security risks is codified by the Open Worldwide Application Security Project (OWASP) in the [OWASP Top Ten](https://owasp.org/www-project-top-ten/). This is the starting point for the `team` when considering attack vectors in a web application's threat model.

### Coding best security practices
- Do we need to copy [this](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md#managing-access-and-content-of-public-and-private-data-stores) [content](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md#writing-defensive-code)
- Moving secrets to backend - secrets should not be exposed to the client-side
- Bot detection - e.g. CAPTCHA

### Encrypted Data & Traffic

- HTTPS
- WSS
- SSL/TLS
- Client-side storage of sensitive data
- `private` cache-control
- ...

### Authentication & Authorization

Broken access control was the top security risk in the 2021 OWASP top ten. The two steps that are required for successful access control are authentication (verifying identity), and authorization (verify permission).

- Cookies (including HTTP only)
- Token handling and storage e.g. JWTs
- Protecting routes on client-side routing (SPAs)

### Cross Site Attacks

#### Cross-Site Scripting (XSS)

#### Cross-Site Request Forgery (CSRF)

#### Cross-Origin Resource Sharing (CORS)

### Security Headers

The following are response headers that the `team` use to protect web applications. They should be configured with policies according to the web app's usage and threat model.

- `Content-Security-Policy` to declare a policy for trusted application sources from which the browser can load resources such as scripts, stylesheets, images, fonts, etc.
- `X-Frame-Options` to declare whether the web app can be placed into an iframe on another domain
- `Strict-Transport-Security` to declare that the website requires HTTPS for encrypted subsequent requests
- `Referrer-Policy` to control what, if any information is included in the `Referer` header for network requests
- `X-Content-Type-Options` to prevent MIME sniffing attacks and force the declared content type instead of allowing a browser to interpret it, leaving room for malicious manipulation

### Secure deployment

- Do we need to copy https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md#maintaining-a-secure-and-up-to-date-foundation-for-deployed-applications?

### Dependency Management

- Keeping deps up to date
- Preventing Supply Chain attacks
- Vulnerability audits

### Security testing & monitoring

- Pen testing
- Fuzzing
- SAST/DAST
- Active monitoring & incident response 
