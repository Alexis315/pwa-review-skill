# PWA Review Report

**URL:** https://example.com
**Date:** 2026-02-04 14:30 UTC
**Overall Score:** 132/150 — Grade: A (Excellent PWA)

## Score Overview

```
Overall: [█████████████████████████████░░] 132/150
```

| Category | Score | Bar |
|----------|-------|-----|
| Manifest Compliance | 18/20 (90%) | `[█████████░] 18/20` |
| Advanced Manifest | 11/13 (85%) | `[████████░░] 11/13` |
| Service Worker & Caching | 26/28 (93%) | `[█████████░] 26/28` |
| Offline Capability | 8/10 (80%) | `[████████░░] 8/10` |
| Installability | 12/13 (92%) | `[█████████░] 12/13` |
| Security | 12/16 (75%) | `[███████░░░] 12/16` |
| Performance Signals | 14/14 (100%) | `[██████████] 14/14` |
| UX & Accessibility | 12/12 (100%) | `[██████████] 12/12` |
| SEO & Discoverability | 6/7 (86%) | `[████████░░] 6/7` |
| PWA Advanced | 13/17 (76%) | `[███████░░░] 13/17` |

## Warnings

These items need improvement:

- **[Security]** No CSP meta tag detected
  - CSP via HTTP header is preferred and not detectable from HTML alone.
- **[Security]** HSTS header not verifiable from HTML
- **[Security]** Permissions-Policy not verifiable from HTML
- **[SEO & Discoverability]** No canonical URL
- **[PWA Advanced]** No handle_links — links may open in browser
- **[PWA Advanced]** iOS Safari lacks support for: push notifications

## Passed Checks

### Manifest & Advanced
- **[Manifest]** name: 'Test Progressive Web App'
- **[Manifest]** short_name: 'TestPWA' (7 chars)
- **[Manifest]** start_url: '/'
- **[Manifest]** display: 'standalone'
- **[Manifest]** Maskable icon found (adaptive icon support)
- **[Manifest]** Icons: 192x192, 512x512
- **[Manifest]** theme_color: '#1a73e8'
- **[Manifest]** background_color: '#ffffff'
- **[Manifest]** scope: '/'
- **[Advanced Manifest]** id: '/'
- **[Advanced Manifest]** description present
- **[Advanced Manifest]** screenshots: 2 (wide + narrow)
- **[Advanced Manifest]** shortcuts: 1 quick actions
- **[Advanced Manifest]** orientation: 'portrait'
- **[Advanced Manifest]** categories: ['utilities']
- **[Advanced Manifest]** display_override: ['window-controls-overlay', 'standalone']
- **[Advanced Manifest]** lang: 'en' (i18n support)
- **[Advanced Manifest]** Web Share Target API configured
- **[Advanced Manifest]** Launch handler configured

### Service Worker
- **[Service Worker]** Service worker registration found
- **[Service Worker]** Install event with precaching
- **[Service Worker]** Activate event with cache cleanup
- **[Service Worker]** Fetch event handler found
- **[Service Worker]** Cache strategy: cache-first + network-first
- **[Service Worker]** Cache versioning detected
- **[Service Worker]** skipWaiting + clients.claim (instant SW updates)
- **[Service Worker]** Push notification handler found
- **[Service Worker]** Notification click handler configured
- **[Service Worker]** Background Sync handler detected
- **[Service Worker]** Navigation preload enabled
- **[Service Worker]** Stale-while-revalidate pattern detected

### Offline & Installability
- **[Offline]** Offline fallback page detected
- **[Offline]** App shell (HTML/CSS/JS) precached
- **[Offline]** Offline state detection in UI
- **[Installability]** Manifest linked in HTML
- **[Installability]** Served over HTTPS
- **[Installability]** SW fetch handler (install requirement)
- **[Installability]** 192x192 icon present
- **[Installability]** 512x512 icon present
- **[Installability]** Apple touch icon (iOS support)
- **[Installability]** Custom install prompt (beforeinstallprompt) detected
- **[Installability]** Custom install UI button found
- **[Installability]** iOS web app capable meta tag

### Security & Performance
- **[Security]** HTTPS enforced
- **[Security]** SRI: 2/2 external resources protected
- **[Security]** No mixed content
- **[Security]** SW scope explicitly restricted
- **[Security]** Error handling in SW
- **[Security]** Referrer-Policy meta tag present
- **[Security]** COOP/COEP headers detected
- **[Performance]** No render-blocking scripts in <head>
- **[Performance]** Lazy loading: 1/1
- **[Performance]** Modern image formats (webp/avif)
- **[Performance]** 2/2 scripts async/defer/module
- **[Performance]** 2 resource hints (preconnect, preload)
- **[Performance]** font-display: swap
- **[Performance]** LCP: Hero image preloaded
- **[Performance]** INP: No blocking event handlers
- **[Performance]** CLS: Images have explicit dimensions
- **[Performance]** Critical CSS inlined in <head>

### UX & SEO
- **[UX & A11y]** Responsive viewport configured
- **[UX & A11y]** Splash screen ready
- **[UX & A11y]** Semantic HTML: 6 landmarks
- **[UX & A11y]** ARIA: 6 attributes
- **[UX & A11y]** lang attribute on <html>
- **[UX & A11y]** iOS status bar styling
- **[UX & A11y]** Theme color meta tag
- **[UX & A11y]** Focus indicators preserved
- **[UX & A11y]** Skip to main content link present
- **[UX & A11y]** Fallback content for JS-disabled browsers (<noscript>)
- **[SEO & Discoverability]** title: 'Test Progressive Web App' (26 chars)
- **[SEO & Discoverability]** meta description: 120 chars
- **[SEO & Discoverability]** Open Graph: og:title, og:description, og:image

### PWA Advanced Capabilities (Unique — Not in Lighthouse)
- **[PWA Advanced]** launch_handler.client_mode: [navigate-existing]
- **[PWA Advanced]** File handler: /open accepts .pdf, .txt
- **[PWA Advanced]** Protocol handler: web+myapp:// → /handle?url=%s
- **[PWA Advanced]** Screenshots with form_factor: wide + narrow
- **[PWA Advanced]** All 1 shortcuts have icons
- **[PWA Advanced]** share_target: POST /share (params: title, text, url)
- **[PWA Advanced]** Web Push: gcm_sender_id configured

## Notes

- **[Advanced Manifest]** Window Controls Overlay enabled — native-like title bar on desktop
- **[Advanced Manifest]** No 'dir' field — defaults to 'auto'
- **[Advanced Manifest]** No note_taking (ChromeOS lock screen notes integration)
- **[Advanced Manifest]** No widgets (Windows 11 Widgets Board integration)
- **[Offline]** No static asset caching in SW
- **[PWA Advanced]** Reuses existing window — prevents duplicate instances
- **[PWA Advanced]** No scope_extensions (single-origin PWA)
- **[PWA Advanced]** No edge_side_panel (Edge sidebar support)
- **[PWA Advanced]** No tabbed display mode (experimental multi-tab)
- **[PWA Advanced]** iOS PWA: No badging API, limited background sync, 50MB storage cap
- **[PWA Advanced]** No iarc_rating_id (IARC age rating for app store distribution)

## Prioritized Recommendations

### Medium Priority (Improvements)

1. **No CSP meta tag detected** (Security)
   - **How to fix:** Add CSP meta tag:
```html
<meta http-equiv="Content-Security-Policy"
  content="default-src 'self'; script-src 'self'; style-src 'self' 'unsafe-inline'">
```
Or better: set via HTTP header.

2. **No canonical URL** (SEO & Discoverability)
   - **How to fix:** Add `<link rel="canonical" href="https://example.com/">` in `<head>`.

3. **No handle_links** (PWA Advanced)
   - **How to fix:** Add `"handle_links": "preferred"` to manifest.json for in-app link handling.

4. **No note_taking** (Advanced Manifest)
   - **How to fix:** Add `"note_taking": { "new_note_url": "/notes/new" }` to manifest.json for ChromeOS integration.

5. **No widgets** (Advanced Manifest)
   - **How to fix:** Add `"widgets"` array to manifest.json for Windows 11 Widgets Board integration.

## Reference Links

- **Security**: https://web.dev/articles/csp
- **SEO & Discoverability**: https://web.dev/articles/discoverable
- **PWA Advanced**: https://developer.chrome.com/docs/capabilities
- **PWA Checklist**: https://web.dev/articles/pwa-checklist
- **Lighthouse**: https://developer.chrome.com/docs/lighthouse

---
*Generated by PWA Review Skill v4.0.0*
