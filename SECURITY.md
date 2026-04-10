# 🔒 Security Policy

## Reporting Vulnerabilities

**Do NOT use public GitHub issues for security reports.**

Email: security@expenseflow.com

We respond within 48 hours and aim to resolve confirmed issues within 10 business days.

## Security Measures

- AES-256 encryption at rest, TLS 1.3 in transit (via Base44)
- Auth handled entirely by Base44 platform
- No raw payment data stored
- All backend functions validate user auth before processing

See [SECURITY.md](SECURITY.md) for the full policy.
