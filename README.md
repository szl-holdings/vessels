# Vessels

> Maritime fleet intelligence.

[![CI](https://github.com/szl-holdings/vessels/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/szl-holdings/vessels/actions/workflows/ci.yml) [![CodeQL](https://github.com/szl-holdings/vessels/actions/workflows/codeql.yml/badge.svg?branch=main)](https://github.com/szl-holdings/vessels/actions/workflows/codeql.yml) [![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/szl-holdings/vessels/badge)](https://securityscorecards.dev/viewer/?uri=github.com/szl-holdings/vessels)
[![Status](https://img.shields.io/badge/status-alpha-C8B26A?style=flat-square)](#status) [![License](https://img.shields.io/badge/license-Proprietary-1F2937?style=flat-square)](./LICENSE) [![Security policy](https://img.shields.io/badge/security-policy-01696F?style=flat-square&logo=github&logoColor=white)](./SECURITY.md)
[![Runtime](https://img.shields.io/badge/runtime-ouroboros%20v6.2.0-2DA44E?style=flat-square)](https://github.com/szl-holdings/ouroboros) [![Runtime tests](https://img.shields.io/badge/runtime%20tests-172%2F172-2DA44E?style=flat-square)](https://github.com/szl-holdings/ouroboros)

Vessels delivers fleet command for maritime operators: sanctions screening, dark-vessel detection, ownership graph analysis, and voyage analytics — built on public AIS feeds with commercial-grade enrichment.

## What Vessels does

- **Fleet command** — live position, voyage state, alarms.
- **Sanctions screening** — ownership and beneficial-owner graph traversal.
- **Dark-vessel detection** — AIS gap analysis with anomaly scoring.
- **Voyage analytics** — route, dwell, port performance, exposure.
- **Compliance audit pack** — evidence bundled per voyage for export controls.

## Architecture

Vessels is a domain surface on the SZL Holdings platform. Every action is routed through the same governed pipeline:

```
sense → structure → correlate → explain → recommend → approve → execute → proof
```

The execution fabric is [**A11oy**](https://github.com/szl-holdings/a11oy). The bounded-loop kernel underneath every domain pack is [**ouroboros**](https://github.com/szl-holdings/ouroboros) — implementing the [Lutar Invariant](https://github.com/szl-holdings/ouroboros-thesis) for measurable convergence with auditable closure.

## Status

**Alpha.** Vessels is under active development as part of the SZL Holdings platform. Public releases are tagged via [GitHub releases](https://github.com/szl-holdings/vessels/releases). Security disclosures: see [SECURITY.md](./SECURITY.md).

## Security & governance

- CI on every push and pull request
- CodeQL static analysis on the default branch and every PR
- OpenSSF Scorecard published weekly, score visible in the badge above
- Dependabot updates, weekly cadence, SHA-pinned actions
- Secret scanning and push protection enabled
- Branch protection: signed commits, required reviews, no force push, no deletion
- Reusable workflows pinned to commit SHAs ([szl-holdings/.github](https://github.com/szl-holdings/.github))

Report a security issue privately via [GitHub Security Advisories](https://github.com/szl-holdings/vessels/security/advisories/new) or [stephen@szlholdings.com](mailto:stephen@szlholdings.com).

## Citation

If you reference Vessels academically or in industry research, use the metadata in [`CITATION.cff`](./CITATION.cff).

## License

Vessels is proprietary. See [LICENSE](./LICENSE) and [NOTICE](./NOTICE). The underlying [ouroboros runtime](https://github.com/szl-holdings/ouroboros) is Apache-2.0 and the [Ouroboros Thesis](https://github.com/szl-holdings/ouroboros-thesis) is CC BY 4.0.

---

**[SZL Holdings](https://szlholdings.com)** · Founder & CEO **Stephen P. Lutar Jr.** · [stephen@szlholdings.com](mailto:stephen@szlholdings.com)

© 2024–2026 SZL Holdings. All rights reserved.
