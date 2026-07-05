# Systems Portfolio — Vaibhav Sharma

A highly interactive, zero-dependency, phosphor-themed developer portfolio for a systems builder. Showcases Linux distros, hardware reverse-engineering, Android bring-up, and full-stack web applications.

**Live Site:** [Nutricalboii.github.io](https://Nutricalboii.github.io)

## Features

- **Systemd Boot Animation:** Custom-tailored systemd-style unit boot sequencing
- **Interactive Terminal:** Linux terminal emulator with `help`, `ls`, `cd`, `cat`, `neofetch`, `git log`, `ps aux`, `tree`, `uptime`, `contact`, tab-completion, and command history
- **Draggable Fan Curve Editor:** Interactive Cairo-mode canvas fan curve editor mapped across temperature/RPM nodes
- **Git Object Model Explorer:** Real client-side SHA-1 git blob computation
- **Round-Robin CPU Scheduler:** Real-time simulation with quantum slice visualizations
- **Diagnostics Drawer Subpages:** Slide-in overlays with detailed project walkthroughs
- **Ctrl+K Command Palette:** System-wide keyboard search and navigation
- **Live Telemetry:** GitHub API integration for follower and repository counts
- **Mobile Hamburger Menu:** Responsive navigation for mobile devices
- **Scroll Reveal Animations:** Progressive disclosure on scroll

## Content

- **Voice-first writing:** All content rewritten to match the authentic voice of the builder
- **Evidence-based:** Projects backed by GitHub data and LinkedIn posts
- **Build log:** Dated entries on real build decisions, not a blog
- **Minor projects:** SMASH for Linux, Telegram Bot, Notum, Sovereign Plate

## Accessibility

- Skip navigation link
- ARIA labels on all interactive elements
- Focus trapping in modals/overlays
- Keyboard-navigable throughout
- Respects `prefers-reduced-motion`
- Screen reader support

## SEO

- Open Graph and Twitter Card meta tags
- JSON-LD structured data
- Canonical URL
- Theme color

## How to Run

```bash
# Open directly in any browser:
xdg-open index.html
```

## Structure

```
.
├── index.html              # Main portfolio (self-contained, 2400+ lines)
├── linkedin_posts.md       # LinkedIn archive (source for content)
├── vaibhav-portfolio-spec.md # Content spec and positioning
├── index_old.html          # Legacy backup (gitignored)
├── LICENSE                 # MIT License
└── README.md               # This file
```

## Content Sources

- LinkedIn posts archive
- GitHub API (real-time data)
- Original spec document

Licensed under the MIT License.
