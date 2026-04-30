# Vessels — Maritime Fleet Intelligence

> AIS tracking, voyage economics, sanctions screening, and dark-vessel detection — unified in a governed command surface for maritime operators.

[![CI](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml/badge.svg)](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/license-Proprietary-red?style=flat-square)](../../LICENSE.md)

[Live Demo](https://szlholdings.com) · [Platform Demo Video](https://szlholdings.com/szl-demo-video/) · [Investor Dashboard](https://szlholdings.com/stephen/investor) · [Architecture](../../docs/architecture/architecture.md) · [Platform Thesis](../../docs/investor/platform-thesis.md)

![Vessels Fleet Command](../../.github/assets/screenshots/vessels-hero.jpg)

---

## What it does

Vessels is the maritime intelligence domain pack for the SZL Holdings platform. It gives fleet operators, risk managers, and compliance teams a single command surface that correlates AIS telemetry, voyage economics, sanctions exposure, and AI-generated alerts — all governed by the same Proof Chain and Covenant Policy infrastructure that runs every SZL Holdings product.

Every anomaly surfaces a recommended action. Every sanctioned-entity match triggers an approval workflow. Every voyage P&L projection is traceable back to the signal that prompted it.

## Run locally

```bash
# From the monorepo root
pnpm install
pnpm --filter @workspace/api-server dev   # Start the API server first
pnpm --filter @workspace/vessels dev
```

**Primary route:** `/vessels/`

> **Note:** AIS telemetry is simulated. Live AIS requires a paid provider subscription (~$15–40K/year). See [`docs/operations/known-gaps.md`](../../docs/operations/known-gaps.md).

## Key modules

| Module | Route | Purpose |
|--------|-------|---------|
| Fleet Overview | `/vessels/` | Fleet status, AIS positions, anomaly alerts |
| Voyage Intelligence | `/vessels/voyages` | Route economics, ETA, deviation detection |
| Sanctions Screening | `/vessels/sanctions` | Entity matching against OFAC/UN/EU lists |
| Dark Vessel Detection | `/vessels/dark` | AIS gap analysis and dark transit alerts |
| Commercial | `/vessels/commercial` | Freight, insurance, and trading modules |

## Tech stack

React 19 + Vite 7 + TypeScript (strict) · Express 5 (shared API server) · PostgreSQL 16 / Drizzle ORM · NOAA CO-OPS / Open-Meteo Marine / GDELT (live) · OIDC/PKCE auth · Proof Chain audit trail

## Architecture reference

Full system architecture: [`docs/architecture/architecture.md`](../../docs/architecture/architecture.md)

---

**SZL Holdings** · [szlholdings.com](https://szlholdings.com) · [inquiries@szlholdings.com](mailto:inquiries@szlholdings.com)


---
## About this repository

This is a public showcase of one product in the [SZL Holdings platform](https://github.com/szl-holdings/szl-holdings-platform) monorepo. It mirrors the README from the platform artifact directory; the canonical, version-controlled source — including the React app, tests, and infrastructure — lives in the platform repo.

All seven products share the same operational substrate:

- **[`@workspace/ouroboros`](https://github.com/szl-holdings/ouroboros)** — bounded loops with measurable convergence; proof-route resolver, risk-tier escalation gate, and almanac cycle advancer.
- **[`@workspace/codex-kernel`](https://github.com/szl-holdings/szl-holdings-platform/tree/main/packages/codex-kernel)** — decision receipts, validators, replay, and trace-hash verification.
- **The Ouroboros Thesis v2** — [`szl-holdings/ouroboros-thesis`](https://github.com/szl-holdings/ouroboros-thesis) — the architectural rationale.

© 2026 SZL Holdings. All rights reserved.
