# GOOT Luxury Frontend / Security Review

## Implemented in this standalone build
- No inline executable JavaScript; main script is external.
- External links use `noopener noreferrer`.
- Booking input is validated client-side before submission.
- No secrets, API keys, credentials, or payment data are embedded in the frontend.
- `aria-live` status for booking feedback and keyboard-visible navigation controls.
- Reduced-motion support is included in CSS.

## Required before production
- Put the site behind HTTPS and HSTS.
- Add a real server-side booking API; never trust browser validation.
- Use strict Content-Security-Policy headers from the server, with nonces/hashes if needed.
- Add rate limiting, request-size limits, CSRF protection where cookie auth is used, server-side schema validation, secure cookies, authentication/RBAC for staff, audit logs and secret management.
- Connect payments only through a PCI-compliant provider; never store raw card data.
- Configure security headers: CSP, HSTS, X-Content-Type-Options, Referrer-Policy, Permissions-Policy and frame protections.
- Run dependency scanning, SAST/DAST, accessibility audit, Lighthouse/Core Web Vitals testing and an authorized staging penetration test before launch.
- Obtain written permission/licensing for GOOT-owned images/video before commercial deployment.
