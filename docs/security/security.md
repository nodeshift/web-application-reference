# Security

## Overview

Security is strongest from conscious design at the outset, rather than retroactively filling gaps after a solution has been built. In this respect, security should be considered at every stage of the application's lifecycle. IBM & RedHat call this practice [Security and Privacy by Design (SPbD)](https://www.redbooks.ibm.com/abstracts/redp4641.html) and recommend it for all systems, including web applications.

This section focuses on the experiences the `team` have had when building web applications to defend against and mitigate security threats.

---

## Relevant Resources From [Node.js Reference Architecture](https://github.com/nodeshift/nodejs-reference-architecture)

1. [Secure Development Process](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md#secure-development-process)
1. [Cross Origin Communication](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/cross-origin.md)

## Guidance

Since security should feature in all components of the application life-cycle, the `team` have found it helpful to start with understanding an application's security landscape in a 'threat model'. This informs the practitioner with a prioritised list of threats as well as mitigations and methods of validation. The rest of this section includes examples of threats, mitigations, and tools that the `team` have found useful to consider.

### Threat Modeling

A [threat model](https://www.ibm.com/garage/method/practices/code/threat-modeling/) should be considered based on the attack surface that the Web Application creates. A public-facing web application for highly confidential personal data of high-target public figures may have a very different threat model to an internal web application that doesn't contain sensitive data nor control anything of significant value.

Depending on the resources available, a threat model can be as informal as simple conversations, to as detailed as a 'threat model workbook'. The workbook is a collection of documentats, diagrams and processes that evolves with the application over time to form an up-to-date threat model. In general, the higher the value of the application and its data, the greater the emphasis should be on having a more detailed threat model.

When considering what can go wrong, the consensus of the most critical security risks is codified by the Open Worldwide Application Security Project (OWASP) in the [OWASP Top Ten](https://owasp.org/www-project-top-ten/). This is called a threat list, and is often the starting point for the `team` when considering attack vectors in a web application's threat model. However, the OWASP Top Ten is just one example of a threat list and indeed threat lists is just one method of threat detection. Each application should will differ and therefore other threat detection methods like the [STRIDE](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats#stride-model) categorisation model are also useful to consider.

Further threat modeling resources:

1. [OWASP Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)
1. [OWASP Threat Dragon](https://owasp.org/www-project-threat-dragon/)

### Coding Best Security Practices

#### Keeping Secrets Secure

Web applications often need access to protected systems like databases, and third-party services. These systems usually use credentials like passwords and API keys for access management. These credentials should be kept secret and should not be exposed to unauthorised users or they will be able to steal and use the credentials to access the data or services. Since client-side code is exposed to users, even if the route is protected from some users, these credentials should not be sent to the client e.g. in client JavaScript.

Instead, these secrets should be securely stored on a server, which should carry out necessary functionality on behalf of the client for example by fetching data from a database before writing it to the DOM, or returning the data in a specialised format like JSON or XML to the client. Since the user has no visibility to the internals of the server, the credentials can be kept out of reach from end-users.

#### Bot Detection & Prevention

If a web page contains user-submittable content, content that should not be easily copied, or content that uses a large amount of server compute, then we recommend considering applying a form of bot protection to prevent spam, web scraping, or unnecessarily expending compute. You should first consider if bots are intended to be able to access the web page's content, for example search engine crawlers. Pages like login or registration pages may be highly targeted, for example in credential stuffing attacks which look to try to see if previously leaked email and password combinations have been reused on other applications. For pages or actions that should be protected from bots, these are some of the mitigating tools to limit or prevent this kind of activity that the `team` have used:

1. CAPTCHA services like [hCaptcha](https://www.hcaptcha.com/) or [reCAPTCHA](https://www.google.com/recaptcha/about/)
1. Edge Bot Management Services like [Akamai Bot Manager](https://www.akamai.com/products/bot-manager) or [Cloudflare Bot Management](https://www.cloudflare.com/products/bot-management/)

Rate limiting

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
- @roastlechon can talk about IBM's experience rolling custom auth before moving to KeyCloak and then to OAuth & OIDC

### Securing Cookies

### Cross Site Attacks

#### Cross-Site Scripting (XSS)

#### Cross-Site Request Forgery (CSRF)

#### Cross-Origin Resource Sharing (CORS)

### Security Headers

The following are response headers that the `team` use to protect web applications. They should be configured with policies according to the web app's usage and threat model. I general heuristic the `team` use is to keep the policies as restrictive as possible, and only to reduce the restrictions if functionally necessary.

- `Content-Security-Policy` to declare a policy for trusted application sources from which the browser can load resources such as scripts, stylesheets, images, fonts, etc. The `team` start with a restrictive policy like `default-src 'self'`, and allow-list other sources if needed.
- `X-Frame-Options` to declare whether the web app can be placed into an iframe on another domain. The `team` start with setting this to `DENY`, and only ease the restriction if required.
- `Strict-Transport-Security` to declare that the website requires HTTPS for encrypted subsequent requests. The `team` sets this to `max-age=63072000; includeSubDomains; preload` as recommended by [Chromium](https://hstspreload.org/), though this can be altered if required e.g. due to network or subdomain incompatibility with HTTPS.
- `Referrer-Policy` to control what, if any information is included in the `Referer` header for network requests. This can also be set as a `meta` tag in the `head` of an HTML document, or within an anchor tag, however the `team` try to find the most scalable method e.g. including the policy as a header set by the web application framework. This policy can be more granular if required, like if some links require the `Referer` header for analytics or affiliate programmes.
- `X-Content-Type-Options` to prevent MIME sniffing attacks and force the declared content type instead of allowing a browser to interpret it, leaving room for malicious manipulation. The `team` sets this to `nosniff`.

### Secure Deployment

Secure deployment has been introduced in the Node.js Reference Architecure section on [secure development processes](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/secure-development-process.md#maintaining-a-secure-and-up-to-date-foundation-for-deployed-applications)

### Dependency Management

- Keeping deps up to date
- Preventing Supply Chain attacks
- Vulnerability audits

### Security Testing & Monitoring

- Pen testing
- Fuzzing
- SAST/DAST
- Active monitoring & incident response
