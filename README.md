# Systems Portfolio — Vaibhav Sharma

A highly interactive, zero-dependency, phosphor-themed developer portfolio showcasing systems engineering, kernels, custom distro builds, and full-stack web applications.

**Live Site:** [Nutricalboii.github.io](https://Nutricalboii.github.io)

## Features

- **Systemd Boot Animation:** Custom-tailored systemd-style unit boot sequencing
- **Interactive Terminal:** Linux terminal emulator with `help`, `ls`, `cd`, `cat`, `neofetch`, `git log`, `ps aux`, `tree`, tab-completion, and command history
- **Draggable Fan Curve Editor:** Interactive Cairo-mode canvas fan curve editor mapped across temperature/RPM nodes
- **Git Object Model Explorer:** Real client-side SHA-1 git blob computation
- **Round-Robin CPU Scheduler:** Real-time simulation with quantum slice visualizations
- **Diagnostics Drawer Subpages:** Slide-in overlays with detailed project walkthroughs
- **Ctrl+K Command Palette:** System-wide keyboard search and navigation
- **Live Telemetry:** GitHub API integration for follower and repository counts

## Accessibility

- Skip navigation link
- ARIA labels on all interactive elements
- Focus trapping in modals/overlays
- Keyboard-navigable throughout
- Respects `prefers-reduced-motion`

## How to Run

```bash
# Open directly in any browser:
xdg-open index.html
```

## Structure

```
.
├── index.html              # Main portfolio (self-contained)
├── index_old.html          # Legacy backup
├── LICENSE                 # MIT License
└── README.md               # This file
```

Licensed under the MIT License.
