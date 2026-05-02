# 0xVera Trace

Modular SaaS-style platform for logistics, inventory, orders, transport, and traceability, with multi-tenant isolation, optional reseller hierarchy, and module licensing. The system is delivered as a **strict polyrepo**: separate repositories for API, web, admin, mobile, shared packages, and deployment orchestration.

Built and maintained as part of real-world infrastructure and production environments.

> Public overview repository. Source code and production infrastructure are private.

## What it does

- Provides a **single HTTP API** (OpenAPI / Swagger as the contract) consumed by web, admin, Android, and integrations.
- Separates **tenant-facing** experience from an **internal admin** surface (different client applications, aligned to the same API).
- Models **identity, tenancy, licensing, and modules** so capabilities can be enabled per tenant without exposing unrelated features.
- Covers bounded domains such as inventory, warehouse operations, orders, transport, billing hooks, integrations, and (where licensed) advanced scenarios such as waste tracking or distributed traceability anchors.
- Ships **deployment orchestration** (reverse proxy, service wiring) as its own component alongside application repos.

## Why it exists

Organizations need one coherent operational stack for stock, fulfilment, and traceability instead of ad-hoc spreadsheets and disconnected tools. The design targets **B2B SaaS**: clear tenancy, commercial module boundaries, and a stable API for long-lived integrations and field clients.

## Key Features

- **Multi-tenant** data model with explicit tenant (and reseller) context on authenticated requests.
- **Role model** including platform superadmin, reseller administration, tenant operations, and customer-portal style access (as documented in the private codebase).
- **Modular licensing** so features are gated by license, not only by UI.
- **OpenAPI-first** backend contract for all first-party clients.
- **Polyrepo governance** per component: independent versioning, CI, and release lines (no monorepo at workspace root).
- **Android client** for operational workflows aligned to the same API.
- **Optional blockchain traceability** treated as a bounded domain when business and compliance require it (design-level; implementation scope is private).

## Architecture Overview

- **API / Backend** — REST API, authorization, domain modules, OpenAPI/Swagger, persistence (PostgreSQL as the documented default relational store).
- **Web** — TypeScript client for tenant and end-user workflows.
- **Admin** — TypeScript administrative SPA served separately from the public web (e.g. under a dedicated path behind the edge proxy).
- **Mobile** — Android application consuming the public API contract.
- **Shared packages** — TypeScript types and DTOs shared across services and clients (consumption strategy is versioned; details are private).
- **Orchestration / edge** — Compose-based stack: reverse proxy routing to API, static admin, and static web as documented in the private deployment repo.
- **Data layer** — Relational database; optional Redis for sessions, cache, or queues depending on phase (as described in internal architecture docs).
- **Automation layer** — Background workers may live inside the API service or split later; exact topology is intentionally not specified here.

## Tech Stack

Verified from the private polyrepo (representative, not exhaustive):

- **Backend:** Node.js (LTS line as pinned in the API repo), TypeScript, Express, Drizzle ORM, PostgreSQL client, Zod, Swagger UI for OpenAPI.
- **Frontends:** TypeScript SPAs (Vite-based toolchain where applicable).
- **Mobile:** Android (native client repo).
- **Platform:** Docker Compose, Nginx at the edge of the application stack.
- **Quality:** Vitest (API), TypeScript compiler pipeline.

## Current Status

**In active development.**

This is a **modular product** under continuous engineering: architecture, domain boundaries, and phased delivery are documented in private repositories. It is **not** a throwaway demo or an abandoned concept—scope grows in controlled phases while keeping contracts and tenancy explicit.

## Screenshots / Demo

<!--
Add screenshots or GIFs here:
![Demo](./assets/demo.gif)
-->

## Notes

This repository is a public overview only. The source code, deployment details, hostnames, registry configuration, and private infrastructure are not exposed.

## Contact

LinkedIn:  
https://www.linkedin.com/in/joel-domenech/
