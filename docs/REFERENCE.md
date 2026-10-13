# AI-Coach-App- source reference


Source reviewed: [`fd911cedb767`](https://github.com/noel-ult/AI-Coach-App-/commit/fd911cedb76767bd4449c3106cfa08db64ed15dc).

This reference records the checked-in source, scripts, configuration names, and route declarations. It is a navigation aid; service availability and successful test execution require separate verification.

## Package commands

Run each command in the directory containing its package manifest. A declared script is not necessarily a passing check; guides call out placeholders and known mismatches.

### mobile-app/package.json

| Script | Shell command |
| --- | --- |
| `start` | `expo start` |
| `android` | `expo start --android` |
| `ios` | `expo start --ios` |
| `web` | `expo start --web` |

Manifest: [mobile-app/package.json](../mobile-app/package.json).

## HTTP route declarations

Paths are **as declared in each source file**. Router/blueprint mount prefixes from the entry point must be prepended; the project guide describes the active entry point and common prefixes. Alternate entry points (such as SQLite) are listed separately by file. Authentication, request bodies, and response schemas live in the linked handlers/models.

| Source | Method | Declared path | Handler |
| --- | --- | --- | --- |
| [backend/app.py](../backend/app.py) | GET | `/` | `index` |
| [backend/app.py](../backend/app.py) | POST | `/api/study-sessions` | `log_study_session` |
| [backend/app.py](../backend/app.py) | GET | `/api/study-sessions` | `get_study_sessions` |
| [backend/app.py](../backend/app.py) | GET | `/api/study-insights` | `get_study_insights` |
| [backend/app.py](../backend/app.py) | GET | `/api/study-recommendations` | `get_study_recommendations_endpoint` |
| [backend/app.py](../backend/app.py) | GET | `/api/study-predictions` | `get_study_predictions` |
| [backend/app.py](../backend/app.py) | POST | `/api/mobile/login` | `mobile_login` |
| [backend/app.py](../backend/app.py) | GET | `/api/mobile/stats` | `mobile_stats` |
| [backend/app.py](../backend/app.py) | GET | `/api/mobile/study-groups` | `mobile_study_groups` |

## Existing documentation

Historical plans/reports describe their own revision; use current source when they disagree.

- [ARCHITECTURE.md](../ARCHITECTURE.md)
- [ENHANCED_FEATURES_SUMMARY.md](../ENHANCED_FEATURES_SUMMARY.md)
- [FEATURES_IMPLEMENTED.md](../FEATURES_IMPLEMENTED.md)
- [MIGRATION_SUMMARY.md](../MIGRATION_SUMMARY.md)
- [QUICKSTART.md](../QUICKSTART.md)
- [README.md](../README.md)
- [STARTUP_CHECKLIST.md](../STARTUP_CHECKLIST.md)
- [backend/requirements.txt](../backend/requirements.txt)
- [mobile-app/MOBILE_README.md](../mobile-app/MOBILE_README.md)
- [mobile-app/README.md](../mobile-app/README.md)
- [mobile-app/assets/README.md](../mobile-app/assets/README.md)

## Source and configuration map

Generated lockfiles, binary assets, compiled output, vendored dependencies, and cached bytecode are omitted. Test files remain listed so coverage can be located.

- [backend/app.py](../backend/app.py)
- [backend/enhanced_analyzer.py](../backend/enhanced_analyzer.py)
- [backend/recommendation_engine.py](../backend/recommendation_engine.py)
- [backend/requirements.txt](../backend/requirements.txt)
- [backend/study_analyzer.py](../backend/study_analyzer.py)
- [backend/test_study_coach.py](../backend/test_study_coach.py)
- [backend/validation_utils.py](../backend/validation_utils.py)
- [demo_enhanced_features.py](../demo_enhanced_features.py)
- [mobile-app/app.json](../mobile-app/app.json)
- [mobile-app/app/_layout.js](../mobile-app/app/_layout.js)
- [mobile-app/app/dashboard.js](../mobile-app/app/dashboard.js)
- [mobile-app/app/groups.js](../mobile-app/app/groups.js)
- [mobile-app/app/index.js](../mobile-app/app/index.js)
- [mobile-app/babel.config.js](../mobile-app/babel.config.js)
- [mobile-app/config.js](../mobile-app/config.js)
- [mobile-app/package.json](../mobile-app/package.json)
- [test_api.py](../test_api.py)
- [test_enhanced_analyzer.py](../test_enhanced_analyzer.py)
