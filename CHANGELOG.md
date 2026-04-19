# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.1] - 2026-04-19

### Changed
- Bumped dependencies: FastAPI 0.136.0, uvicorn 0.44.0, aiomysql 0.3.2
- Docker base image bumped to Python 3.14-slim
- GitHub Actions: `actions/checkout` v6, `docker/setup-buildx-action` v4, `docker/build-push-action` v7

### Added
- Full open-source project meta: `CHANGELOG.md`, `CONTRIBUTING.md`, `SECURITY.md`, `CODE_OF_CONDUCT.md`, GitHub issue/PR templates, Dependabot config, Docker build GitHub Actions workflow, README badges

## [0.1.0] - 2026-04-06

Initial release.

- Read-only HTTP API exposing Uptime Kuma monitor metadata and latest heartbeats
- API key authentication via `X-API-Key` header (constant-time comparison)
- Optional CIDR-based IP range allowlist (`ALLOWED_RANGES`)
- `X-Forwarded-For` respected for reverse-proxy deployments
- Healthcheck endpoint at `/health`
- Distroless-style container via `Dockerfile`
- GHCR image publishing on tag via GitLab CI
