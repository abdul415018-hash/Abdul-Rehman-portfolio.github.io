# Security Specification for Portfolio Firestore Rules

## 1. Data Invariants
- `portfolio/data`: The master website content is publicly readable by all clients to enable consistent multi-browser display of portfolio items, styling, and selected template. Writing or modifying this configuration is strictly restricted to verified administrator (`abdul415018@gmail.com`).
- `messages/{messageId}`: Public visitors can create contact inquiries with strict field limits (`name`, `email`, `message`, etc.). Reading, listing, updating, or deleting messages is restricted to the administrator (`abdul415018@gmail.com`).
- Default Deny: All other paths are blocked (`allow read, write: if false;`).

## 2. Dirty Dozen Security Test Payloads
1. Unauthenticated write to `portfolio/data` -> REJECT (PERMISSION_DENIED)
2. Authenticated non-admin write to `portfolio/data` -> REJECT (PERMISSION_DENIED)
3. Spoofed email with unverified token to `portfolio/data` -> REJECT (PERMISSION_DENIED)
4. Unauthenticated read from `messages` collection -> REJECT (PERMISSION_DENIED)
5. Non-admin read from `messages` collection -> REJECT (PERMISSION_DENIED)
6. Message creation with oversized name (> 100 chars) -> REJECT (PERMISSION_DENIED)
7. Message creation with oversized message (> 2000 chars) -> REJECT (PERMISSION_DENIED)
8. Message creation with invalid ID characters -> REJECT (PERMISSION_DENIED)
9. Message update by public visitor -> REJECT (PERMISSION_DENIED)
10. Message deletion by public visitor -> REJECT (PERMISSION_DENIED)
11. Write to arbitrary root document `/secrets/passwords` -> REJECT (PERMISSION_DENIED)
12. Portfolio data write with missing required attributes -> REJECT (PERMISSION_DENIED)
