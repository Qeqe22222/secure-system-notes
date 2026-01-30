# XSS & CSP (Content Security Policy)

## Problem
XSS happens when attacker-controlled input becomes executable script in the browser.

## Risk
- Account takeover (cookie/session theft)
- Data exfiltration
- Malicious actions under user context

## Secure Design Approach
1. Output escaping (templates should escape by default)
2. Input validation (limit unexpected characters where appropriate)
3. Add CSP as a mitigation layer:
   - Start with: `default-src 'self'`
   - Avoid inline scripts where possible
   - Consider nonce-based scripts if needed

## Checklist
- [ ] Auto-escaping enabled in templates
- [ ] No raw user HTML rendered without sanitization
- [ ] CSP enabled with restrictive defaults
- [ ] Inline scripts minimized
