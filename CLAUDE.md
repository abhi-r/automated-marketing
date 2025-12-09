# Digital Marketing Automation Service - Documentation Portal

## Project Overview

This is a **static HTML documentation portal** for an automated digital marketing managed service targeting SMBs. The service uses AI to generate and publish social media content across multiple platforms.

**Key Concept:** This is a *managed service* (not a SaaS product). Customers pay for outcomes (posts published, presence maintained), not for tool access. The complexity of AI tools, APIs, and automation is hidden from customers.

## File Structure

```
/Users/abhishek/Desktop/marketing/
├── marketing-service-docs.html    # Main documentation portal (single-file HTML/CSS/JS)
├── Context Chat 1.rtf             # UI/UX feedback and pending improvements
├── Context Chat 2.rtf             # DIY architecture deep-dive (Blotato, N8N)
├── Digital-Marketing-Automation-Research.docx  # Tool comparison research
├── CLAUDE.md                      # This file - project context for Claude Code
└── .claude/
    └── settings.local.json        # Claude Code settings
```

## Architecture

### Tech Stack (DIY Approach)
- **Orchestration:** N8N (self-hosted on ~$15/mo VPS)
- **Content Generation:** Claude API (Haiku) - ~$5-10/customer/month
- **Video Generation:** InVideo AI ($28/mo shared)
- **Publishing:** Blotato ($29/mo) - THE KEY LINCHPIN
  - Single API normalizes access to TikTok, Instagram, YouTube, Facebook, LinkedIn
  - Handles OAuth, token refresh, platform audits
  - Community N8N node (requires self-hosted N8N, not N8N Cloud)
- **Data Store:** Google Sheets (free)

### Service Tiers
| Tier | Price | Platforms | Posts/Week | Content Types |
|------|-------|-----------|------------|---------------|
| Basic | $500/mo | 3 | 3/platform | Text + Image |
| Growth | $999/mo | 5 | 5/platform | + Video (2-3/week) |
| Premium | $2,000+/mo | Unlimited | 7+/platform | All formats, custom |

### Unit Economics
- Fixed costs: ~$77/mo (N8N + Blotato + InVideo)
- Variable costs: ~$5-15/customer/month
- **Gross margin: 97%+** at scale

## Documentation Portal Features

The `marketing-service-docs.html` file is a single-page application with:

### Dual Document Views
1. **Operational Plan** - Business processes, customer journey, onboarding, team roles
2. **Technical Plan** - Architecture, APIs, integrations, data flows, monitoring

### UI Features
- **Dark mode** with system preference detection and manual toggle
- **Page transitions** (fade effect) when switching between documents
- **Dropdown navigation** for document selection
- **Collapsible TOC** with smooth scroll
- **Sticky header** with current section indicator
- **Responsive design** (mobile-friendly)

### Design System
- Display font: Fraunces (serif)
- Body font: Source Sans 3
- Mono font: JetBrains Mono
- Accent color: #EA580C (orange)
- Max content width: 860px

## Code Conventions

### CSS
- All colors use CSS variables (`:root { --color-* }`)
- Dark mode via `@media (prefers-color-scheme: dark)` and `[data-theme="dark"]`
- Spacing uses `--space-*` variables (xs, sm, md, lg, xl, 2xl)

### JavaScript
- Vanilla JS only (no frameworks)
- Functions: `switchTab()`, `toggleTheme()`, `toggleDocSelector()`, `toggleTocItem()`, `scrollToTop()`
- Theme preference stored in `localStorage.getItem('theme')`

### HTML Structure
- Sections use `<section id="..." data-section="Display Name">`
- Tables wrapped in `<div class="table-wrapper">`
- Callouts use `.callout`, `.callout.warning`, `.callout.danger`, `.callout.success`, `.callout.info`
- Code blocks use `.config-block` with `.comment`, `.key`, `.value` spans

## Platform Integration Notes

### Most Permissive
- **Meta (Facebook/Instagram):** Full automation supported, 100 posts/day
- **X (Twitter):** Full automation supported

### Restrictions Apply
- **LinkedIn:** PUBLISH ONLY via official partners. No engagement automation (will suspend account)
- **Google Business Profile:** Must use authorized tools (Buffer, Hootsuite)

### Requires Business Accounts
- **TikTok:** Business Account + OAuth via Blotato (no direct API recommended)
- **YouTube:** Brand Account, 10K quota/day (~6 uploads/day)

## Pending Improvements

From `Context Chat 1.rtf`:
- [x] Dark mode with system preference
- [x] Page transition animations
- [x] TOC styling fixes
- [x] Header dropdown navigation
- [x] Platform Requirements section
- [x] TikTok integration expansion
- [x] YouTube documentation
- [x] Cost breakdown tables

## Working With This Project

### To edit the documentation:
1. Open `marketing-service-docs.html` in a code editor
2. HTML content is organized by `<!-- Section X: Name -->` comments
3. CSS is in the `<style>` block at the top
4. JavaScript is in the `<script>` block at the bottom

### To preview:
Simply open `marketing-service-docs.html` in any modern browser. No build step or server required.

### To add a new section:
1. Add TOC entry in the `<nav class="toc">` for the appropriate plan
2. Add section content with `<section id="..." data-section="...">`
3. Use existing callouts, tables, and process-flow components for consistency

## Related Resources

- **Blotato:** Multi-platform publishing API
- **N8N:** Workflow automation (use self-hosted for community nodes)
- **InVideo AI:** AI video generation
- **Claude API:** Content generation (Haiku model recommended for cost)
