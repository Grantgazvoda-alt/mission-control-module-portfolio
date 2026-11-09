# Portfolio Map — Canonical Repository Routing

MCM maintains the authoritative map of which repository owns which product. The full inventory covers thirteen repositories across Official Intelligence, Your Potential AI, Revolution Intelligence, GummyBearGummy, BitForge, and independent projects. Highlights:

## Canonical sources

| Product | Canonical repository | Stack |
| --- | --- | --- |
| Your Potential AI (YOAI) | `official-intelligence-ri-ypa/Your-potential-1` | TanStack Start, React, TypeScript, Cloudflare Workers, D1 |
| Revolution Intelligence | `Grantgazvoda-alt/revolutionintelligence.us` | FastAPI, PostgreSQL, SQLAlchemy, JWT/RBAC, encrypted storage, Render |
| GummyBearGummy | `Grantgazvoda-alt/gummybeargummy` | TanStack Start, React 19, Cloudflare Workers, 215 tests |
| BitForge code engine | `Grantgazvoda-alt/website-project-homepage` | Seven-agent sequential pipeline: architect → frontend → backend → database → API → DevOps → reviewer |
| BitForge project hub | `Grantgazvoda-alt/bitfordge` | TanStack Start dashboard over GitHub stats |
| Independent AI assistant | `Grantgazvoda-alt/revolution-base` | FastAPI, SQLite, multi-provider LLM adapters, SSE, Docker/Render |
| Portfolio operations | `Grantgazvoda-alt/agent-platform` | Shell health checks, GitHub Actions, governance docs |
| Justice for Gina | `Grantgazvoda-alt/justiceforgina` | Static site, GitHub Pages, security headers |

## Lineage preserved

Archived prototypes (early Next.js Revolution build, Lovable-generated UI, backend-centric thin kernel, mission/research reference repo) are kept for provenance. They are not treated as production sources.

## Governance rules

1. Resolve the company before editing anything.
2. Use the canonical repository unless an explicit migration is approved.
3. Never merge code, data, credentials, or billing across companies without a contract.
4. Treat operational claims as stale until re-verified against current evidence.
5. Preserve archived history. Do not rewrite it.

## Open decisions tracked

- BitForge: consolidate code engine and project hub, or keep separate?
- Assistant naming: `revolution-base` misleads; rename or reassign.
- Portfolio monitoring: replace obsolete targets with canonical domains.
- Enterprise migration: which personal-account repos move into the org?
- Higgsfield independence: audit workspace-package and deployment-injection dependencies.
- Empty-repo cleanup: define or archive placeholders.
