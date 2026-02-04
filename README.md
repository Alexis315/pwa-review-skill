# PWA Review Skill for Claude Code

A comprehensive Progressive Web App audit skill that goes beyond standard Lighthouse testing. Analyzes PWAs across **10 categories** with a **150-point scoring system**, including advanced features that typical audits miss.

## Features

- **150-point scoring system** across 10 categories
- **Beyond Lighthouse**: Checks advanced PWA features like `handle_links`, `launch_handler`, `file_handlers`, `protocol_handlers`
- **Core Web Vitals signals**: LCP, INP, and CLS optimization detection
- **Enhanced Security**: HSTS, CSP, Permissions-Policy, COOP/COEP checks
- **Install Experience**: beforeinstallprompt and custom install UI detection
- **Actionable reports**: Each issue includes specific fix recommendations
- **No dependencies**: Runs natively in Claude Code using WebFetch

## Categories Evaluated

| Category | Points | What It Checks |
|----------|--------|----------------|
| Manifest Compliance | 20 | Required manifest fields (name, icons, display, colors) |
| Advanced Manifest | 13 | Screenshots, shortcuts, i18n, maskable icons, widgets, note_taking |
| Service Worker & Caching | 28 | Registration, events, cache strategies, skipWaiting, clients.claim, push, navigation preload |
| Offline Capability | 10 | Fallback pages, app shell, offline indicators |
| Installability | 13 | HTTPS, manifest link, beforeinstallprompt, custom install UI |
| Security | 16 | CSP, SRI, HTTPS, COOP/COEP, HSTS, Permissions-Policy |
| Performance Signals | 14 | Render-blocking, lazy loading, resource hints, Core Web Vitals signals |
| UX & Accessibility | 12 | Viewport, semantic HTML, ARIA, focus indicators, skip links |
| SEO & Discoverability | 7 | Meta tags, Open Graph, structured data |
| **PWA Advanced** | 17 | Cutting-edge PWA capabilities, Web Push |

## Grading Scale

| Grade | Score Range | Percentage |
|-------|-------------|------------|
| A+ | 135+ points | 90%+ |
| A | 120-134 points | 80-89% |
| B | 105-119 points | 70-79% |
| C | 90-104 points | 60-69% |
| D | 60-89 points | 40-59% |
| F | <60 points | <40% |

## Installation

### Method 1: Add to Claude Code Skills (Recommended)

1. Copy the `SKILL.md` file to your Claude Code skills directory:
   ```bash
   # macOS/Linux
   cp SKILL.md ~/.claude/skills/pwa-review.md

   # Or create a custom skills folder
   mkdir -p ~/.claude/skills
   cp SKILL.md ~/.claude/skills/pwa-review.md
   ```

2. Restart Claude Code or reload skills

### Method 2: Project-Level Skill

Add `SKILL.md` to your project's `.claude/` directory:

```
your-project/
├── .claude/
│   └── skills/
│       └── pwa-review.md
└── ...
```

## Usage

Once installed, invoke the skill with:

```
/pwa-review https://your-pwa-url.com
```

### Example

```
/pwa-review https://looknex.com
```

Claude will:
1. Fetch the HTML from the URL
2. Discover manifest and service worker locations
3. Analyze both files against the 150-point checklist
4. Generate a detailed report with scores and recommendations

## Sample Output

```markdown
# PWA Audit Report

**URL:** https://example.com
**Date:** 2026-02-04
**Overall Score:** 132/150 (88%) — Grade: A

## Score Breakdown

| Category | Score | Status |
|----------|-------|--------|
| Manifest Compliance | 18/20 | ✅ |
| Advanced Manifest | 11/13 | ✅ |
| Service Worker & Caching | 26/28 | ✅ |
| Offline Capability | 10/10 | ✅ |
| Installability | 12/13 | ✅ |
| Security | 12/16 | ⚠️ |
| Performance Signals | 14/14 | ✅ |
| UX & Accessibility | 12/12 | ✅ |
| SEO & Discoverability | 5/7 | ⚠️ |
| PWA Advanced | 12/17 | ⚠️ |

## Critical Issues
- None

## Warnings
- Missing Content Security Policy
- Missing canonical URL
- No file_handlers defined

## Recommendations
...
```

## What Makes This Different from Lighthouse

| Feature | Lighthouse | PWA Review Skill |
|---------|------------|------------------|
| `handle_links` check | ❌ | ✅ |
| `launch_handler` analysis | ❌ | ✅ |
| `file_handlers` validation | ❌ | ✅ |
| `protocol_handlers` check | ❌ | ✅ |
| `share_target` analysis | ❌ | ✅ |
| `edge_side_panel` support | ❌ | ✅ |
| `scope_extensions` check | ❌ | ✅ |
| `note_taking` (ChromeOS) | ❌ | ✅ |
| `widgets` (Windows 11) | ❌ | ✅ |
| `skipWaiting`/`clients.claim` | ❌ | ✅ |
| Navigation preload | ❌ | ✅ |
| Stale-while-revalidate | ❌ | ✅ |
| `beforeinstallprompt` | ❌ | ✅ |
| Push/notificationclick | ❌ | ✅ |
| Cache strategy analysis | Basic | Detailed |
| iOS-specific guidance | Limited | Comprehensive |

## v4.0.0 New Checks

### Service Worker & Caching (+6 points)
- `skipWaiting()` instant activation
- `clients.claim()` immediate control
- Navigation preload
- Stale-while-revalidate pattern
- Push event handler
- notificationclick handler

### Installability (+3 points)
- `beforeinstallprompt` handling
- Custom install UI detection

### Security (+4 points)
- HSTS header
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy

### Performance Signals (+4 points)
- LCP optimization signals
- INP optimization signals
- CLS prevention
- Critical CSS inlined

### UX & Accessibility (+2 points)
- Focus indicators visible
- Skip to main content link

### Advanced Manifest (+2 points)
- `note_taking` (ChromeOS)
- `widgets` (Windows 11)

### PWA Advanced (+2 points)
- Web Push configured
- Notification permission UX

## Contributing

Contributions welcome! Please submit issues and PRs to improve the checklist or add new checks.

## License

MIT License - see [LICENSE](LICENSE) for details.

## Resources

- [Web App Manifest | web.dev](https://web.dev/add-manifest/)
- [Service Workers | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
- [PWA Checklist | web.dev](https://web.dev/pwa-checklist/)
- [Workbox | Google](https://developer.chrome.com/docs/workbox/)

---

**Version:** 4.0.0
**Author:** [@emrahub](https://github.com/emrahub)
