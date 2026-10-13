# AI Study Coach — SQLite edition

A Flask study-session API with rule-based analysis and an Expo/React Native client. This repository is the SQLite edition; the similarly named Supabase repository has a different backend contract.

## Backend setup

```sh
python3 -m venv .venv
.venv/bin/pip install -r backend/requirements.txt
.venv/bin/python backend/app.py
```

The development API listens on port 5000 and initializes tables at startup. It uses `backend/study_coach.db`, which is already tracked. Preserve any data you need before running experiments. There is no external model key requirement: the analysis and recommendation engines are Python rules.

## Mobile setup

```sh
cd mobile-app
npm install
npm start
```

Set `API_CONFIG.BASE_URL` in `mobile-app/config.js` to your development machine's reachable address. A physical phone's localhost refers to the phone, not your computer. The committed address is machine-specific.

The mobile configuration contains stale `/sessions` and `/log` endpoints. The backend implements `GET /api/study-sessions` and `POST /api/study-sessions`; API integration needs to use those actual routes. The mobile login and study-group endpoints provide demonstration behavior rather than a complete account/group system.

## API and data model

Create a session with JSON fields `subject`, `duration` in minutes, `focus_level`, and `difficulty`. Ratings are 1–5; duration validation uses 1–1440 minutes. The backend exposes session listing, insights, recommendations, predictions, mobile stats, and demo groups. `StudySession` and the routes live in `backend/app.py`; analyzer and recommendation modules handle calculations.

## Checks and limitations

The unittest suite is `backend/test_study_coach.py`. Run it only in a disposable checkout: it changes the URI after SQLAlchemy initialization and calls `drop_all`, so it may still affect the configured SQLite file. From `backend/`, the intended command is `python -m unittest test_study_coach`. Root API scripts expect a running server; inspect their writes first.

The development entry uses debug mode and binds all interfaces. A shared deployment needs a production server, durable data handling, and real authentication. The historical README tree mentions directories absent from this edition; use the source reference for the current inventory.

## More documentation

- [Source, command, and configuration reference](REFERENCE.md)
- [Contributing](../CONTRIBUTING.md)
