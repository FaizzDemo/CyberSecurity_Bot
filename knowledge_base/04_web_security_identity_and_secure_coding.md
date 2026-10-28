# Web Security, Identity, and Secure Coding

## 1. How Web Applications Work

A browser sends requests to a server. The server processes requests and may communicate with databases or other services before returning a response.

Security depends on authentication, authorization, input handling, configuration, data storage, dependencies, and monitoring.

## 2. Authentication

Authentication verifies a user's identity.

Common methods include passwords, security keys, authenticator applications, and other multi-factor authentication mechanisms.

Good practices:
- Use established authentication libraries.
- Enable MFA for important accounts.
- Apply rate limits to login attempts.
- Protect account recovery processes.
- Avoid revealing unnecessary login information.

## 3. Authorization

Authorization determines what an authenticated user can do.

Check permissions on the server for every sensitive operation. Hiding a button in the user interface does not protect the underlying data.

For example, a student should not be able to view another student's private records simply by changing an identifier in a URL.

## 4. Session Security

Applications often use sessions or tokens to maintain a user's authenticated state.

Defensive practices include:
- Use HTTPS.
- Set appropriate cookie attributes, including `Secure`, `HttpOnly`, and `SameSite`.
- Regenerate session identifiers after login or privilege changes.
- Set appropriate expiration periods.
- Revoke sessions when necessary.
- Never expose session secrets in URLs or logs.

A stolen valid session token may allow unauthorized access until it expires or is revoked.

## 5. Input Validation

Treat user-controlled input as untrusted.

Validate expected types, formats, lengths, ranges, and business rules on the server.

Input validation is important, but it does not replace safe database queries or context-aware output encoding.

## 6. SQL Injection

SQL injection occurs when unsafe handling of input changes the meaning of a database query.

Defenses:
- Use parameterized queries or prepared statements.
- Avoid constructing SQL through string concatenation with user input.
- Apply least-privilege database permissions.
- Avoid exposing detailed database errors to users.
- Use trusted database libraries.

## 7. Cross-Site Scripting (XSS)

XSS occurs when an application causes untrusted content to execute as script in another user's browser.

Defenses:
- Use context-aware output encoding.
- Use safe templating features.
- Avoid dangerous DOM manipulation.
- Handle user-supplied HTML carefully.
- Consider Content Security Policy as an additional layer.

Input filtering alone does not guarantee XSS prevention.

## 8. Cross-Site Request Forgery (CSRF)

CSRF can cause a browser to submit an unwanted authenticated request.

Depending on the authentication design, defenses may include anti-CSRF tokens, SameSite cookies, origin checks, and additional confirmation for sensitive actions.

## 9. Secure File Uploads

File-upload features can expose applications to malicious files, storage abuse, and resource exhaustion.

Defensive practices:
- Allow only required file types.
- Check file contents as well as extensions.
- Limit file sizes and processing time.
- Generate server-side filenames.
- Store uploads outside executable web directories where possible.
- Check access permissions.
- Avoid executing uploaded files.
- Protect against path traversal and unsafe archive extraction.

## 10. Password Storage

Never store passwords as plaintext.

Use a purpose-built password hashing algorithm, such as Argon2id, scrypt, or bcrypt, with suitable parameters and salts.

Plain SHA-256 is not an appropriate standalone password-storage solution because it is designed to be fast.

Use a trusted authentication library when possible.

## 11. Secrets Management

Secrets include API keys, database passwords, and signing keys.

- Do not commit secrets to GitHub.
- Keep local secret files in `.gitignore`.
- Use environment variables or a secrets manager.
- Restrict access to secrets.
- Rotate exposed credentials.
- Keep secrets out of frontend code.

If a secret is published accidentally, revoke or rotate it. Deleting it from the latest version alone may not remove it from Git history.

## 12. Dependency Security

Third-party packages can contain vulnerabilities.

Use trusted packages, maintain dependency lock files, update dependencies, monitor security advisories, and remove unused libraries.

## 13. Secure Development Checklist

- Validate input on the server.
- Use parameterized database queries.
- Encode untrusted output appropriately.
- Check authorization for sensitive operations.
- Protect sessions and credentials.
- Keep dependencies updated.
- Limit file-upload size and type.
- Log security events without recording passwords or tokens.
- Test access-control boundaries.
- Back up important data.

## 14. Safe Practice Exercises

In a local application you own:

1. Add server-side validation to a form.
2. Replace unsafe SQL construction with parameterized queries.
3. Create two test accounts and verify that private records remain separated.
4. Add file-upload limits.
5. Check the project for accidentally committed secrets.

Do not test vulnerabilities on websites without explicit authorization.

## 15. Review Questions

1. What is the difference between authentication and authorization?
2. How do parameterized queries prevent SQL injection?
3. Why is input validation alone insufficient for preventing XSS?
4. Why should API keys not be committed to GitHub?
5. What makes file uploads safer?
6. Why must access control be checked on the server?

## 16. Answers

1. Authentication verifies identity; authorization checks permitted actions.
2. Parameterized queries separate data from SQL instructions.
3. XSS prevention also requires safe output encoding and appropriate handling of browser contexts.
4. Published secrets may be copied or retained in repository history.
5. Type and size restrictions, safe filenames, controlled storage, authorization, and safe processing reduce risk.
6. Client-side controls can be bypassed, so the server must enforce permissions.
