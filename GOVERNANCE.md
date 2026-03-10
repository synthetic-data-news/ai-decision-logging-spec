# Governance

## Overview

The AI Decision Logging Specification is an open standard maintained by a community of contributors. This document describes how decisions are made, how the specification evolves, and how contributors can participate.

---

## Guiding Principles

1. **Openness** — Specification development happens in public. Issues, proposals, and decisions are visible to all.
2. **Consensus** — Changes require broad agreement among active contributors, not just maintainers.
3. **Stability** — Published versions are immutable. Breaking changes require a new major version.
4. **Implementation neutrality** — The specification defines format and verification rules, not implementation architecture. It must remain equally implementable by any compliant system.
5. **Regulatory alignment** — Changes should consider alignment with EU AI Act, NIST AI RMF, and emerging global AI governance frameworks, without normatively depending on any single regulation.

---

## Roles

### Maintainers
Maintainers are responsible for:
- Reviewing and merging pull requests
- Releasing new versions (following semver)
- Enforcing the code of conduct
- Maintaining the issue tracker and roadmap

Current maintainers are listed in [CITATION.cff](CITATION.cff).

### Contributors
Anyone who submits an issue, pull request, or participates in discussion is a contributor. Contributions of all kinds are valued — bug reports, schema feedback, implementation reports, editorial improvements.

### Implementors
Organizations or individuals who implement the specification. Implementors are encouraged to register in [REFERENCE_IMPLEMENTATIONS.md](REFERENCE_IMPLEMENTATIONS.md) and participate in shaping the spec.

---

## Change Process

### Minor Changes (patch/minor version)
- Editorial corrections, clarifications, and non-breaking additions
- Submitted as a pull request with clear rationale
- Requires approval from at least one maintainer
- Released as patch (x.x.N) or minor (x.N.0) version

### Breaking Changes (major version)
- Any change that would invalidate previously conformant records or implementations
- Must be proposed as a GitHub issue first, with a written rationale
- Open for community comment for at least 30 days
- Requires consensus among active contributors (no sustained objection from implementors)
- Released as a new major version (N.0.0)
- Prior major version enters maintenance mode (security/critical fixes only) for 12 months

### Schema Changes
- JSON Schema changes follow the same process as spec changes
- Additive (non-breaking) schema changes may be released as minor versions
- `additionalProperties: false` is intentional — new fields require a spec update

---

## Versioning

This specification follows [Semantic Versioning 2.0.0](https://semver.org/):

- **MAJOR** — Incompatible changes to the record format, hash algorithm, or signature scheme
- **MINOR** — Backwards-compatible additions (new optional fields, new conformance levels)
- **PATCH** — Clarifications, editorial fixes, typo corrections

The current version is in [VERSION](VERSION).

---

## Decision Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-03-01 | Initial v0.1.0 published | Formalize format developed in practice |
| 2026-03-01 | Ed25519 selected as sole signature algorithm | Wide support in standard libraries; avoid algorithm agility complexity |
| 2026-03-01 | RFC 8785 JCS selected for canonicalization | Deterministic; widely implemented; avoids custom serialization rules |
| 2026-03-01 | SHA-256 selected for hash chaining | FIPS-approved; sufficient for audit integrity; quantum migration deferred to v1.0 |

---

## Code of Conduct

Contributors are expected to engage respectfully and constructively. This project follows the [Contributor Covenant](https://www.contributor-covenant.org/) Code of Conduct.

---

## Contact

Open an issue on GitHub for questions about governance, or to propose a governance change.
