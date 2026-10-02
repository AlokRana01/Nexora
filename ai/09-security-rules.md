# Security Engineering Rules

Security must be considered for every meaningful application change.

---

## 1. Never Expose Secrets

Never hardcode:

- API keys
- Passwords
- Tokens
- Private credentials
- Database credentials
- Access tokens

Use the project's secure configuration mechanism.

---

## 2. Inspect Existing Security

Before modifying authentication, authorization, data handling, or external integrations:

Inspect the current implementation.

---

## 3. Input Validation

Validate untrusted input before using it.

Consider:

- Type
- Format
- Length
- Range
- Encoding
- Allowed values

---

## 4. File Handling

For uploaded files:

- Validate file type
- Validate size
- Avoid unsafe paths
- Avoid arbitrary execution
- Handle malformed input safely

---

## 5. Database Safety

Use safe parameterized database operations.

Never construct unsafe queries from raw user input.

---

## 6. Authentication and Authorization

Do not assume authentication means authorization.

Verify that users are permitted to access the requested resource or action.

---

## 7. Sensitive Data

Avoid logging sensitive information.

Do not expose:

- Passwords
- Tokens
- Personal credentials
- Private keys
- Sensitive user data

---

## 8. Dependency Security

Before introducing dependencies:

Consider whether the dependency is trustworthy and maintained.

---

## 9. Security Changes Require Testing

After security-related changes:

- Test expected behavior
- Test invalid input
- Test unauthorized behavior where applicable
- Run relevant security checks

---

## 10. Do Not Claim "Secure"

Security is contextual.

Report specific verified protections instead of making broad unsupported claims.