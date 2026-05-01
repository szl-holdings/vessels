# Vessels — Maritime Intelligence

  > Maritime fleet intelligence with sanctions screening, dark-vessel detection, and voyage P&L — every conclusion backed by a decision receipt.

  [![CI](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml/badge.svg)](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![License](https://img.shields.io/badge/license-Proprietary-red?style=flat-square)](../../LICENSE.md)

  [Live Demo](https://szlholdings.com) · [Platform Demo Video](https://szlholdings.com/szl-demo-video/) · [Investor Dashboard](https://szlholdings.com/stephen/investor) · [Architecture](../../docs/architecture/architecture.md)

  ![Vessels — Maritime Intelligence](https://raw.githubusercontent.com/szl-holdings/.github/main/assets/screenshots/vessels-maritime.jpg)

  ---
  ## What it does

  Vessels is the **maritime fleet intelligence command** — sanctions screening, dark-vessel detection, voyage economics, marine insurance, and commodity trading. Live API surfaces wire to the platform database with explicit `dataSource: 'live' | 'demo' | 'simulated'` flags on every response, so operators always know the provenance of what they see.

  ## Government alignment

  Vessels is positioned for federal/state maritime, border security, and sanctions enforcement workflows:

  - **NIST AI RMF**: full coverage across GOVERN / MAP / MEASURE / MANAGE
  - **Sanctions screening**: OFAC SDN list integration with primary-source hashing
  - **Dark-vessel detection**: AIS-gap analysis with risk tier escalation to human review
  - **Marine insurance + commodity trading**: live database persistence (insurance/trading routes wired to `marineInsurance{Quotes,Policies,Claims}Table` and `commodityTrading{Orders,Positions,Fills}Table` as of the 2026-04-30 platform consolidation pass)

  ## Run locally

  ```bash
  pnpm install
  pnpm --filter @workspace/api-server dev
  pnpm --filter @workspace/vessels dev
  ```

  **Primary route:** `/vessels/`

  ## Tech stack

  React 19 + Vite 7 + TypeScript (strict) · Express 5 · PostgreSQL 16 / Drizzle ORM · Mapbox GL · OFAC SDN integration · Ouroboros loop runtime (`PRF_SYSTEM_CLAIMS`) · Codex decision receipts
  
  ---

  **SZL Holdings** · [szlholdings.com](https://szlholdings.com) · [inquiries@szlholdings.com](mailto:inquiries@szlholdings.com)

  ---
  ## About this repository

  This is a public showcase of one product in the [SZL Holdings platform](https://github.com/szl-holdings/szl-holdings-platform) monorepo. It mirrors the README from the platform artifact directory; the canonical, version-controlled source — including the React app, tests, and infrastructure — lives in the platform repo.

  All seven products share the same governed substrate:

  - **[`@workspace/ouroboros`](https://github.com/szl-holdings/ouroboros)** — bounded loops with measurable convergence, v6 ecosystem layer, government readiness module (**133/133 tests**)
  - **[`@workspace/codex-kernel`](https://github.com/szl-holdings/szl-holdings-platform/tree/master/packages/codex-kernel)** — decision receipts, validators, replay, trace-hash verification
  - **The Ouroboros Thesis** — [`szl-holdings/ouroboros-thesis`](https://github.com/szl-holdings/ouroboros-thesis) — architectural rationale + v6 operational contract

  Government readiness audit (NYSTEC pre-briefing, 2026-04-30): [`docs/audit/szl-government-readiness.md`](https://github.com/szl-holdings/ouroboros/blob/main/docs/audit/szl-government-readiness.md)

  © 2026 SZL Holdings. All rights reserved.
  