# AI-Coach-App-: verification and operations

Reviewed against [default-branch commit 378a6b541a71](https://github.com/noel-ult/AI-Coach-App-/commit/378a6b541a713a8536197ebe41c3a3c232b693cd) on 2026-10-28. Start with the [developer guide](PROJECT_GUIDE.md) for installation and architecture, and the [source reference](REFERENCE.md) for exact scripts, configuration readers, routes, and source locations.

## SQLite study sessions

Use disposable SQLite data to create sessions, inspect insights and recommendations, and check mobile/API response compatibility. Review test setup before running tests that drop tables.

These are acceptance scenarios for a maintainer to run in the documented environment. Their inclusion is not a claim that live integrations or production credentials were tested during this documentation update.

## Deployment and failure diagnosis

Configure the mobile base URL for the device rather than assuming localhost reaches the development machine. Keep debug development settings out of shared hosting.

## Maintaining the contract

When behavior changes, update the guide and examples in the same PR. Check the entry point and working directory before copying commands. Use the linked source readers to distinguish build-time configuration from process environment. For failures, capture the first application error, runtime version, selected mode, and redacted configuration names before later proxy or port errors.

Keep changes tied to evidence: a declared command is not proof it passes, a process health response is not a successful end-to-end workflow, and a historical report describes its own revision. Record actual check results and any unavailable external services in the PR.
