# Systems Portfolio — Vaibhav Sharma

A highly interactive, zero-dependency, phosphor-themed developer portfolio showcasing systems engineering, kernels, custom distro builds, and full-stack web applications.

👉 **Live Site:** [Nutricalboii.github.io](https://Nutricalboii.github.io) (or host it anywhere directly as a single static index.html)

## 🛠️ Features Included

- **Systemd Boot Animation:** Custom-tailored systemd-style unit boot sequencing.
- **Interactive Terminal:** An execution environment simulating a Linux terminal with working commands (`help`, `ls`, `cd`, `cat`, `pwd`, `neofetch`, `git log`, `ps aux`, `tree`, tab-completion, and command history).
- **Draggable Fan Curve Editor:** Fully interactive, Cairo-mode canvas fan curve editor mapped across temperature/RPM nodes (from LOQ Control Center spec).
- **Git Object Model Explorer:** Real client-side SHA-1 git blob computation (`blob {len}\0{content}`) to inspect git hash-object structures.
- **Round-Robin CPU Scheduler:** Real-time simulation of process scheduler with quantum slice visualizations and interactive step triggers.
- **Diagnostics Drawer Subpages:** Clean, digital Diagnostic drawer overlays that slide-in from the right with detailed project walkthroughs and interactive elements.
- **Ctrl+K Command Palette:** System-wide keyboard search and navigate overlay to jump between views and trigger actions dynamically.
- **Live Telemetry:** Connects to GitHub API to pull live follower and repository counts dynamically.

## 📁 Repository Structure

```bash
.
├── index.html         # Main portfolio entrypoint (fully self-contained)
├── index_old.html     # Old structure backup
└── README.md          # Project documentation
```

## 🚀 How to Run Locally

Since this prototype is fully client-side and optimized with zero dependencies, you can open it directly in any browser:

```bash
# Double click index.html or open via terminal:
xdg-open index.html
```

Licensed under the MIT License.
