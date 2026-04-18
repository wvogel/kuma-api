# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.0] - 2026-04-06

Initial release.

- Read-only HTTP API exposing Uptime Kuma monitor metadata and latest heartbeats
- API key authentication via `X-API-Key` header (constant-time comparison)
- Optional CIDR-based IP range allowlist (`ALLOWED_RANGES`)
- `X-Forwarded-For` respected for reverse-proxy deployments
- Healthcheck endpoint at `/health`
- Distroless-style container via `Dockerfile`
- GHCR image publishing on tag via GitLab CI
