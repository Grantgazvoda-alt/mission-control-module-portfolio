# Health-Check Methodology

## Scope

The checker verifies **public HTTPS reachability** of configured roots. That is the entire claim. It does not verify:

- Authentication or session handling
- Database connectivity or schema integrity
- Provider or billing configuration
- Deployment identity or release version
- Application-level readiness (queues, workers, cron)

## Execution

```bash
bash scripts/health-check.sh            # stdout JSON only
bash scripts/health-check.sh --report  # also writes health-reports/YYYY-MM-DD.md
```

Requirements: Git, Bash, curl. No elevated privileges.

## Output semantics

| Observation | Human output | JSON value |
| --- | --- | --- |
| HTTP 200 | status code | numeric code |
| HTTP 4xx/5xx | status code | numeric code |
| Transport failure (timeout, DNS, TLS) | `000` | `0` |

Any non-200 or zero causes a nonzero exit code so the run is detectable in CI or by a wrapper.

## Why narrow

Broad claims create false confidence. A 200 on a marketing page says nothing about the API behind it. By limiting the check to reachability and labeling everything else as requiring separate evidence, MCM stays honest under audit — which is the point of a health module.

## Report format

Each `--report` run writes a Markdown file with:

- Generation timestamp
- Table of target, URL, status, title
- JSON appendix of raw observations
- Explicit note that the file reflects its generation time only

Files are never overwritten. History accumulates.
