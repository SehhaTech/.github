# Security Policy

SehhaTech is a healthcare management platform, and we take the security of patient and clinic data seriously. We appreciate the efforts of security researchers and users who help us keep the platform safe.

## Supported Versions

As SehhaTech is currently in active early-stage development, security fixes are applied to the latest version on the `main` branch of each repository.

| Version | Supported |
| ------- | --------- |
| Latest (main) | ✅ |
| Older / archived branches | ❌ |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

If you discover a security vulnerability, please report it privately by emailing:

📧 **sehhatech.team@gmail.com**

Please include as much of the following as possible:

- A description of the vulnerability and its potential impact
- Steps to reproduce the issue (proof-of-concept code if applicable)
- The affected repository, endpoint, or component
- Any suggested mitigation, if you have one

### What to expect

- **Acknowledgment:** we aim to confirm receipt of your report within **48 hours**.
- **Initial assessment:** we aim to provide an initial assessment of severity and next steps within **5 business days**.
- **Resolution:** timelines vary depending on complexity and severity, but we will keep you updated throughout the process.
- We ask that you give us reasonable time to address the issue before any public disclosure.

## Scope

This policy covers all repositories under the [SehhaTech organization](https://github.com/SehhaTech), including but not limited to the backend API, frontend web applications, and mobile application.

Particular areas of interest include:

- Authentication and authorization flaws (JWT handling, OTP verification, session/token management)
- Multi-tenant data isolation issues (a clinic being able to access another clinic's data)
- Exposure of patient health information (PHI) or personally identifiable information (PII)
- Injection vulnerabilities (SQL injection, XSS, etc.)
- Misconfigured cloud infrastructure or exposed credentials

## Recognition

We're a small team building this project from the ground up. If you responsibly disclose a valid vulnerability, we're happy to credit you (with your permission) in our release notes or a security acknowledgments page once we have one.

Thank you for helping keep SehhaTech and its users safe.
