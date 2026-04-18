# Security Policy

## Reporting a vulnerability

If you discover a security vulnerability, **please do not open a public issue**.

Report it privately via [GitHub Security Advisories](https://github.com/wvogel/uptime-kuma-api/security/advisories/new).

You will receive an acknowledgement within a few days. Once the issue is
confirmed, a fix is released before the advisory goes public.

## Scope

In scope:

- The `uptime-kuma-api` FastAPI application and its Docker image
- API key validation (timing attacks, bypass) and IP allowlist enforcement
- Any potential SQL injection, read amplification or database escape paths

Out of scope:

- Vulnerabilities in Uptime Kuma itself — report those to
  [louislam/uptime-kuma](https://github.com/louislam/uptime-kuma)
- Misconfigurations in user deployments (exposed ports, missing
  `ALLOWED_RANGES`, weak API keys)

## Hardening notes

- This service opens a **read-only** connection to the Kuma database. It does
  not issue any writes.
- The API key is compared using `hmac.compare_digest` to prevent timing attacks.
- Set `ALLOWED_RANGES` to a narrow CIDR list whenever possible.
- Put the service behind an HTTPS reverse proxy — it speaks plain HTTP inside
  the container.

## Supported versions

Only the latest release on `main` is supported.
