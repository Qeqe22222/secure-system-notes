# Access Control: RBAC & IDOR

## Problem
Users may access resources they should not (e.g., changing an ID in the URL to view others’ data).

## Risk
- Data leakage
- Privilege escalation
- Compliance issues

## Secure Design Approach
1. Enforce **server-side authorization** for every protected action
2. Use **RBAC** for role-level permissions (role → allowed actions)
3. Add **ownership checks** for user-specific resources (prevents IDOR)
4. Deny by default (return 403)

## Common Failure Patterns
- Checking role only in UI, not in backend
- Missing ownership check (classic IDOR)
- Predictable IDs without authorization

## Checklist
- [ ] Authorization enforced server-side for sensitive routes
- [ ] Ownership validated for user-specific resources
- [ ] 403 returned on unauthorized access
- [ ] No reliance on frontend-only restrictions
