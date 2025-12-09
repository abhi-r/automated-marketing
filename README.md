# Digital Marketing Automation Service Documentation

A comprehensive operational and technical documentation portal for an automated digital marketing managed service targeting SMBs.

## Features

- **Dual Document Views:** Operational Plan and Technical Plan with smooth transitions
- **Dark Mode:** System preference detection with manual toggle
- **Responsive Design:** Mobile-friendly layout with sticky header
- **No Backend Required:** Pure HTML/CSS/JavaScript — no dependencies
- **Professional UI:** Clean design system with custom typography and colors

## Viewing the Documentation

**Live:** https://abhi-r.github.io/marketing-docs

**Local:** Open `marketing-service-docs.html` in any browser

## File Structure

- `marketing-service-docs.html` - Main documentation portal (single file, ~3,500 lines)
- `CLAUDE.md` - Project context and development notes
- `README.md` - This file

## Contents

### Operational Plan
1. Executive Summary
2. Service Tiers ($500–$2,000+/mo)
3. Platform Requirements
4. Customer Journey
5. Onboarding Process
6. Content Generation Workflow
7. Publishing & Moderation
8. Reporting & Analytics
9. Edge Cases & Escalations
10. Roles & Responsibilities
11. Risk Mitigation

### Technical Plan
1. Technical Overview
2. Tool Stack & Comparisons
3. Platform Integrations (Meta, LinkedIn, TikTok, YouTube, etc.)
4. Data Flows
5. Authentication & Security
6. Infrastructure & Deployment
7. Monitoring & Alerting

## Technology Stack

- **HTML5** - Semantic structure
- **CSS3** - Variables, dark mode, responsive design, animations
- **Vanilla JavaScript** - No frameworks or dependencies
- **Google Fonts** - Fraunces (display), Source Sans 3 (body), JetBrains Mono (code)

## Development

The entire application is contained in a single HTML file for easy portability.

### To edit:
1. Open `marketing-service-docs.html` in your editor
2. Modify HTML content, CSS styles, or JavaScript functions
3. Refresh browser to see changes immediately

### Key Functions
- `switchTab(tabId)` - Switch between Operational and Technical plans with page transition
- `toggleTheme()` - Toggle dark/light mode with localStorage persistence
- `toggleDocSelector()` - Show/hide dropdown navigation
- `toggleTocItem(event, toggleElement)` - Expand/collapse TOC sections

## Deployment

Hosted on **GitHub Pages** — automatically deploys when you push to the `main` branch.

## Unit Economics

- **Fixed Costs:** ~$77/mo (N8N, Blotato, InVideo AI)
- **Variable Costs:** ~$5-15/customer/month
- **Gross Margin:** 97%+ at scale

## Author

Abhishek Rastogi | December 2025
