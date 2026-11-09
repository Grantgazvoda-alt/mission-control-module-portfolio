# Mission Control Module — Portfolio

**Public showcase of engineering work. Implementation remains proprietary.**

Mission Control Module (MCM) is the operations and governance layer for Official Intelligence's multi-company portfolio: Your Potential AI, Revolution Intelligence, GummyBearGummy, BitForge, and supporting projects. It coordinates repository health, canonical-source routing, and executive reporting across separate product boundaries.

## What it demonstrates

- **Cross-company portfolio governance** — a single map that resolves which repository is canonical for each product, with explicit rules preventing accidental merges of code, credentials, billing, or customer data across company lines.
- **Honest evidence boundaries** — historical health reports are preserved as dated snapshots, explicitly labeled non-current, so operational claims are never presented as live truth without fresh verification.
- **Narrow, verifiable health checks** — a bash-based HTTPS reachability checker that records HTTP status, writes timestamped Markdown reports, and exits nonzero on failure. It deliberately does *not* claim authenticated readiness, database access, or billing status.
- **Issue and PR hygiene** — structured templates for bugs, features, questions, and security issues; a CODEOWNERS file; a contributing guide; a security policy.

## Architecture

See [docs/architecture.md](docs/architecture.md) for the component layout and data flow.

## Health-check methodology

See [docs/health-check-methodology.md](docs/health-check-methodology.md).

## Portfolio map

See [docs/portfolio-map.md](docs/portfolio-map.md) for the canonical-repository routing table.

## License

See [LICENSE](LICENSE). Implementation source is not included in this public repository.
