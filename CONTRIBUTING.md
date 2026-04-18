# Contributing

Thanks for considering a contribution! This API is deliberately small — a
read-only proxy that exposes just enough of the Uptime Kuma database for
external dashboards like [uptime-kuma-status](https://github.com/wvogel/uptime-kuma-status).

## Reporting issues

Before opening an issue please search existing ones. For bugs, include:

- What you expected
- What actually happened
- Steps to reproduce
- Version (commit hash or tag) and Uptime Kuma version

## Proposing features

Open an issue first. This project intentionally stays minimal — new endpoints
or database writes will most likely be rejected. If you need more, a fork is
usually the right answer.

## Pull requests

1. Fork the repo and branch from `main`.
2. Keep the change small and focused.
3. Update `CHANGELOG.md` under `[Unreleased]`.
4. Run the app locally against a real Uptime Kuma database before opening the PR.

## Local development

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

export DB_HOST=localhost DB_PORT=3306 DB_NAME=kuma \
       DB_USER=kuma DB_PASS=secret API_KEY=test
uvicorn main:app --reload --host 0.0.0.0 --port 8080

curl -H "X-API-Key: test" http://localhost:8080/api/monitors
```

## License

By contributing, you agree that your contributions will be licensed under
the project's MIT license.
