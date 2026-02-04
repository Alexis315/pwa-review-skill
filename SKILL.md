---
name: pwa-review
description: Performs comprehensive PWA technical audits analyzing manifest.json, service worker, offline behavior, installability, security, performance, SEO, and UX. Triggered when reviewing PWAs, checking manifests, analyzing service workers, auditing PWA readiness, or when users mention "Lighthouse alternative".
argument-hint: [url]
allowed-tools: Bash, Read, WebFetch
---

# PWA Review Skill

Analyze Progressive Web Apps for technical compliance, performance, and UX quality.

## Quick Start

```
/pwa-review https://example.com
```

**Output**: Scored report with 9 categories (108 pts max), letter grade (A+ to F), and actionable recommendations.

## Workflow

1. **Fetch PWA resources** — Use the WebFetch tool to retrieve the target URL's HTML
2. **Discover manifest and service worker** — Run `scripts/discover_pwa.py` to extract manifest URL and SW registration
3. **Fetch manifest.json** — Use the WebFetch tool on discovered manifest URL
4. **Fetch service worker** — Use the WebFetch tool on discovered SW URL
5. **Run analysis** — Execute `scripts/analyze_pwa.py` with fetched content
6. **Generate report** — Execute `scripts/generate_report.py` to create final .md report
7. **Present report** — Display the generated report to the user

## Step Details

### Step 1-4: Fetching Resources

Fetch the target URL first. Save HTML to a temp file, then discover manifest and service worker paths:

```bash
python3 scripts/discover_pwa.py --html pwa_page.html --base-url "https://example.com"
```

Output: JSON with `manifest_url` and `sw_url` fields.

### Step 5: Analysis

```bash
python3 scripts/analyze_pwa.py \
  --html pwa_page.html \
  --manifest pwa_manifest.json \
  --sw pwa_sw.js \
  --url "https://example.com"
```

Output: JSON analysis at `pwa_analysis.json`

### Step 6: Report Generation

```bash
python3 scripts/generate_report.py \
  --analysis pwa_analysis.json \
  --output pwa_review_report.md
```

### Step 7: Present

Read and display the generated `pwa_review_report.md` to the user.

## Handling Missing Resources

- **No manifest found**: Score manifest category as 0, note as critical finding
- **No service worker**: Score SW/offline categories as 0, note as critical finding
- **Fetch errors**: Note the error, analyze available resources, mention limitations in report

## Scoring Categories (108 pts total)

| Category | Points | Key Checks |
|----------|--------|------------|
| Manifest Compliance | 20 | name, display, icons, theme_color, scope |
| Advanced Manifest | 11 | screenshots, shortcuts, lang, display_override |
| Service Worker | 20 | install/activate/fetch events, cache strategy |
| Offline Capability | 10 | fallback page, app shell, offline indicator |
| Installability | 10 | HTTPS, manifest link, icons, apple-touch-icon |
| Security | 10 | CSP, SRI, mixed content, error handling |
| Performance | 10 | render-blocking, lazy loading, resource hints |
| UX & Accessibility | 10 | semantic HTML, ARIA, viewport, lang |
| SEO & Discoverability | 7 | title, meta description, Open Graph, canonical |

**Detailed scoring**: See [references/pwa-checklist.md](references/pwa-checklist.md)

## Report Output

Reports include:
- Overall score (0-108) with letter grade (A+ to F)
- Category breakdown with individual scores
- Critical findings (blockers)
- Warnings (improvements needed)
- Passed checks
- Prioritized recommendations with "How to Fix" snippets

**Example reports**: See [examples/](examples/)
