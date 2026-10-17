# Changelog

All notable changes to this overview are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project uses [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2026-10-18

### Added

- Screenshots / Demo section with product screenshots (demo data): analytics dashboard, orders list and draft order workflow, traceability business events, and product catalog.

### Changed

- Localization feature now lists all 7 supported UI languages.

## [1.1.0] - 2026-10-18

### Added

- Detailed list of implemented features: JWT authentication with refresh token rotation, PostgreSQL row-level security, 9-role RBAC, inventory, orders, picking and shipping, proof of delivery, traceability event log, webhooks, analytics, media upload, waste tracking MVP with chain of custody, billing MVP with Stripe Checkout, and the offline-first Android field app.
- Roadmap section listing items that are not implemented yet, including network-agnostic blockchain traceability anchoring (design phase).
- Current component versions and the 7 supported UI languages.
- This changelog, linked from the README.

### Changed

- Blockchain traceability moved from the feature list to the roadmap.
- Deployment statement now describes a containerized stack under active development.
- Tech stack updated: Node.js 24 LTS, TypeScript 7, Express 5, PostgreSQL 16, Zod 4, React 19 + Vite, Kotlin + Jetpack Compose, Cosign image signing, GitHub Actions and Dependabot.
- Orchestration repository renamed to `0xvera-trace-orch`.

### Fixed

- Reseller hierarchy is no longer presented as complete.
- Redis is described as currently disabled (optional, future component).

## [1.0.0] - 2026-05-02

### Added

- Initial public overview of 0xVera Trace.
- Architecture diagram and badges.

[1.2.0]: https://github.com/jowy81/0xvera-trace-overview/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/jowy81/0xvera-trace-overview/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/jowy81/0xvera-trace-overview/releases/tag/v1.0.0
