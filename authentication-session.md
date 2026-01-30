# Authentication & Session Security

## Problem
Authentication verifies identity; sessions keep users logged in securely.

## Risk
- Session hijacking
- Credential stuffing / brute force
- Weak reset flows

## Secure Design Approach
1. Store passwords using strong hashing (e.g., Werkzeug/bcrypt/argon2)
2. Use secure session cookies:
   - HttpOnly
   - Secure (HTTPS)
   - SameSite
3. Clear sessions on logout
4. Rate-limit or lock accounts after repeated failures

## Checklist
- [ ] Passwords are hashed, never plaintext
- [ ] Sessions cleared on logout
- [ ] Cookie flags set properly
- [ ] Login attempts protected (rate limit / lockout)
