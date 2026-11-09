# Architecture

## Purpose

MCM sits above the product repositories. It does not contain product code. Its job is observation, routing, and reporting.

## Components

```text
mission-control-module/
├── scripts/health-check.sh      # Manual HTTPS reachability checker
├── health-reports/              # Timestamped Markdown output
├── docs/                        # Portfolio maps, business memory, dashboard specs
├── .github/                     # CODEOWNERS, issue/PR templates, security policy
├── README.md
├── HEALTH_REPORT.md             # Historical snapshot, explicitly non-current
├── LICENSE
├── CONTRIBUTING.md
└── SECURITY.md
```

## Data flow

1. Operator runs `health-check.sh` (optionally with `--report`).
2. Script issues unauthenticated HTTPS GETs to configured public roots.
3. Each response is recorded as status code, title, and timing.
4. A JSON summary is printed to stdout; a Markdown report is written under `health-reports/` when requested.
5. Non-200 or transport failure (`000`) causes a nonzero exit.

No credentials, tokens, or authenticated sessions are used. The checker cannot see behind authentication walls — by design.

## Design decisions

- **Bash + curl, not a framework.** The check is one script with no runtime dependencies beyond Git and curl. It runs anywhere.
- **Reports are append-only history.** Past reports are never rewritten. Each file is a point-in-time observation.
- **Documentation over automation.** At this checkpoint, no scheduler, GitHub Actions workflow, or live dashboard is committed. The manual path is the verified path.
- **Separation of companies.** Product code, customer data, credentials, billing, domains, and legal identities stay in their owning repositories. MCM references them; it does not contain them.

## What is deliberately absent

- No secrets or API keys in the tree.
- No database connection strings.
- No claims of live deployment, billing, or user metrics presented as current.
- No cross-company data merging.
