# Security Policy

This public repository is intended for project overview documentation and safe public materials.

## Sensitive data policy

Do not commit:

- API keys
- Broker credentials
- Webhook URLs
- `.env` files
- Server secrets
- Private account identifiers
- Raw trading logs
- Database dumps
- Internal deployment secrets

## Reporting concerns

If you notice potentially sensitive material in this repository, please open a private communication channel with the maintainer rather than creating a public issue that repeats the sensitive content.

## Project safety posture

Prism separates display-only research and observability layers from real execution.

During Phase 3c, production validation and runtime safety boundaries should not be weakened for convenience or speed.
