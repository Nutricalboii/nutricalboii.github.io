# Portfolio Content Specification — Vaibhav Sharma

A grounded, evidence-based content and structure spec. Every fact below is real (from your GitHub, your projects, our past conversations). Nothing here is invented psychology or fabricated backstory — where a design choice is a *recommendation* rather than a fact, it's labeled as one. Hand this straight to Antigravity IDE as the content layer; pair it with your usual stack (Next.js 14, React 19, TypeScript, Tailwind, FastAPI where a backend demo is needed, Vercel deploy).

---

## 1. Positioning (one line, evidence-backed)

You're a systems builder, not a "full-stack developer with a portfolio." The evidence: you've shipped a custom Linux distro from source (13 rebuilds to first boot), reverse-engineered your own laptop's power management instead of accepting vendor defaults, and you're bringing up Android/Halium on hardware with no public docs (Moto G5 Plus, codename `potter`). Most students build CRUD apps for portfolio filler. You build things that can fail at the hardware layer — and ship them anyway.

**Positioning line (pick one or merge):**
- "I build the layer most developers never touch."
- "Software is where I start. Hardware is where I stop guessing."
- Your existing signature line is already strong and should anchor the About section verbatim:
  > *"I experiment where theory meets hardware, build where failure is possible, and use AI as a tool — because systems that survive reality are never accidental."*

---

## 2. Site Map

```
/                  Hero + one-line positioning + 3 signal projects
/about             Real bio, stack, timeline
/work              All projects, filterable by domain (Systems / Web / AI / Mobile)
/work/[slug]       Individual case study
/leadership        CSI DIT PR work, hackathons (optional — could fold into /about)
/contact           Email, LinkedIn, GitHub, resume download
```

Keep it to 4–5 real pages. Don't build a "photography" or "terminal filesystem" section unless you actually have photography work or want to build a real terminal easter egg — see §6 for a scoped, honest version of that idea.

---

## 3. Hero Section (copy)

```
Vaibhav Sharma
Full-stack + systems developer. B.Tech CSE, DIT University (2027).

I build things that touch hardware, kernels, and production —
not just components.

[View Work]   [Resume]   [GitHub]
```

Avoid: "passionate," "innovative," "dedicated" — replace with what you actually did (see case studies).

---

## 4. About Section (grounded facts only)

- 3rd-year B.Tech CSE student, DIT University Dehradun, graduating January 2027.
- Head of Public Relations, CSI DIT University (900+ member technical chapter).
- Full-stack internship at Codec Technologies (Dec 2025–Jan 2026, AICTE & ICAC approved).
- Scored 89/90 on a DSA quiz (CSN307: arrays, trees, graphs, Java algorithms).
- Perfect score at a Meta AI Hackathon with Disaster-Response-OpenEnv (Team Singularity, with Anushka Rawat and Devesh Khurana).
- Built ScholarSync at Google GDSC TechSprint Hackathon.
- Honest stack: JavaScript, TypeScript, Python, Next.js, Node.js, Express, FastAPI, MongoDB, ChromaDB, Electron, Fastify, WebCrypto, GTK4, Linux, Bash, Git, REST APIs, PyQt5. You use AI tools (Claude, Gemini, GPT) and Antigravity IDE to move faster — the architecture decisions, debugging, and persistence are yours.

Write this as 2–3 short paragraphs, not a list. Let the projects carry the weight; the About page just orients the reader.

---

## 5. Project Case Studies

Use this template for every case study page:

```
Problem → Approach → Stack → What broke → Current state
```

Below are real drafts for your core projects. Fill in specific metrics/screenshots as you have them — don't round up.

### Vaelix OS
**Problem:** Wanted a Linux distro that reflected your own workflow and hardening preferences instead of accepting a stock distro's defaults.
**Approach:** Built on Ubuntu 24.04 + KDE Plasma + XanMod kernel. Took 13 rebuilds to reach first clean boot.
**Stack:** Linux build tooling, XanMod, KDE Plasma.
**Current state:** v1.1 "Titanium Velocity" shipped. v2.0 "Renaissance" planned — Wayland, Rust core components, GrapheneOS-inspired hardening, a Kali sandbox via Podman.
**What to show:** boot screenshots, the rebuild-count story (it's a real, honest "here's what didn't work" narrative — use it, don't hide it).

### LOQ Control Center
**Problem:** Your Lenovo LOQ laptop's power/thermal management was a black box controlled by vendor software you couldn't inspect or extend.
**Approach:** Reverse-engineered the laptop's power behavior on Ubuntu and built a full custom control system.
**Stack:** Python, GTK4, systemd, D-Bus, Polkit, RAPL (CPU PL1/PL2), nvidia-smi (GPU cTGP), Cairo-rendered fan curve editor with 7 draggable points, Fn+Q four-profile cycling, UPower D-Bus for AC detection.
**Current state:** v2.0.1, 6 releases, targets common LOQ laptop models generally (not just yours).
**What to show:** the fan curve editor UI — this is your most visually demonstrable systems project, put it front and center.

### Android 13 LineageOS Bring-up (Moto G5 Plus, codename `potter`)
**Problem:** No maintained LineageOS/Halium support for this device; wanted to build it from source.
**Approach:** Kernel 3.18, Soong/Ninja build system, VINTF configuration. Active 3+ months. Separately attempted a Halium 9.0/Ubuntu Touch bring-up on the same device — diagnosed black-screen/initramfs panics, completed two kernel builds (~15.29 MiB each), resolved rootfs flashing, SELinux, and display driver config. Hit a boot freeze at "device can't be trusted" that's currently unresolved; paused.
**Stack:** C++, Soong/Ninja, kernel-level debugging.
**Current state:** honest framing — this is in progress, and that's fine to say directly. "Currently blocked at X, here's what I've ruled out" is more credible than pretending it's finished.

### ScholarSync
**Problem:** Built for Google GDSC TechSprint Hackathon.
**Stack:** Next.js 14, FastAPI, ChromaDB, Gemini 2.0 Flash.
**Current state:** Live on Vercel.
**What to show:** live link, the RAG/retrieval angle (ChromaDB + Gemini) since that's the technically interesting part.

### Notum
**Problem:** Wanted a password/secrets vault where you don't have to trust the server with plaintext.
**Approach:** Zero-knowledge design — encryption happens client-side.
**Stack:** Electron, Fastify, WebCrypto, AES-256-GCM.
**What to show:** the zero-knowledge architecture diagram (client never sends the server anything it can decrypt) — this is a strong, explainable security story.

### The Sovereign Plate
**Stack:** Node.js, Express, MongoDB, Twilio.
**Current state:** Live, real client-facing product.

### Sharma Digital X-Ray Lab
**Stack:** React 19, Firebase.
**Current state:** Live client project, bilingual (English/Hindi) — worth mentioning since it's a real deployed product for an actual business, not a toy project.

### Vitalis (in progress)
**Problem:** Personal health/fitness tracking with real wearable data instead of manual entry.
**Approach:** PRD scoped deliberately narrow — Google Fit and Fitbit integration only, via OAuth2/REST, rather than trying to support everything.
**Stack:** Next.js 14, React 19, TypeScript, FastAPI, MongoDB Atlas.
**What to show:** the scoping decision itself is worth a sentence — "I scoped this to two integrations on purpose" signals judgment, not just code.

### Avora Ventures
**Problem:** A venture-building/AI-solutions studio concept, not just a landing page.
**Approach:** Comprehensive PRDs and phased roadmaps built for an Antigravity IDE checkbox-driven workflow. Recent work: full site overhaul targeting Apple/Google-level polish — scroll animations, UX pass.
**Stack:** Next.js 14, React 19, TypeScript, Tailwind, FastAPI, MongoDB Atlas, Vercel.
**Live:** github.com/Nutricalboii/Avora

### Disaster-Response-OpenEnv (Meta AI Hackathon)
**Result:** Perfect score, Team Singularity (you, Anushka Rawat, Devesh Khurana).
**What to show:** this is a credibility signal for AI/ML work — give it real estate even if the repo itself is small.

### Vaultflow (concept-stage, be honest about this)
**Problem:** Payment-system observability — "Datadog for payment systems."
**Approach:** Go microservices, TimescaleDB, React dashboard.
**Current state:** long-term open-source ambition, not yet built. Either omit from the live site until there's something to show, or include it explicitly under a "What's next" section — don't present a concept as a finished project.

---

## 6. The Terminal Idea — Scoped Honestly

The instinct (an interactive terminal easter egg with commands like `whoami`, `ls`, `neofetch`) is genuinely good *because it's true to you* — you actually work in terminals daily, this isn't a costume. Keep it, but scope it small and real:

- `whoami` → returns your actual one-line bio.
- `ls projects/` → lists your real repos, `cd`-able to real case study pages.
- `neofetch` → a stylized version showing real stats (years coding, current stack, current project) instead of fake system info.
- Skip anything that requires inventing fictional content (fake "dreams/" or "ideas/" directories with content that doesn't exist yet). If a directory exists, it should resolve to something real.

This is a good scope for a first build: 4–5 commands, real data, no fabricated flavor text.

---

## 7. Design Direction (recommendation, not fact)

Grounded in what you've actually built and used repeatedly: dark KDE/GTK environments, minimal watch aesthetic, GTK4 tooling, terminal-first workflows. A reasonable, non-invented design direction:

- **Palette:** near-black background (not pure #000), single accent color used sparingly, no gradients-as-decoration.
- **Type:** one serif or distinct display face for headings (identity), a clean sans for body, a monospace face for code/terminal sections (you already live in monospace all day — use a real one like JetBrains Mono or Berkeley Mono, not a decorative "hacker" font).
- **Motion:** short, functional only — reveal information, don't decorate. 150–200ms transitions, no particle effects, no autoplay video/audio.
- **Imagery:** real screenshots of your actual tools (LOQ Control Center's fan curve editor, Vaelix OS desktop, terminal sessions) over stock photography or 3D renders.

This is a stronger design story than "cyberpunk hacker aesthetic" because every visual choice maps to something you've actually built, not a mood board.

---

## 8. GitHub README Overhaul

Your current pinned repos (ScholarSync, loq-control, The-Sovereign-Plate, android_device_motorola_potter, telegram-affiliate-bot, android13) are already a strong, honest set — systems work alongside shipped products. Keep that mix; it's more credible than an all-web-app pinned list.

README structure recommendation:
```
1. One-line identity + signature quote (exact, as always):
   "I experiment where theory meets hardware, build where failure is
   possible, and use AI as a tool — because systems that survive
   reality are never accidental."
2. Current focus (2-3 bullets, real and current: Vitalis, Avora, Vaelix 2.0)
3. Stack badges — only tools you'd defend in an interview
4. Pinned repos (keep current mix of systems + shipped products)
5. Footer: secondary quote, exact:
   "Most people wait to be ready. I just start — because the only way
   to know if something holds is to put pressure on it."
```

Don't add stat-farming badges (follower count, "profile views") — they read as filler next to genuinely hard projects like the Halium bring-up.

---

## 9. Contact / Footer

Keep it simple and real:
```
vaibhav282227@gmail.com
linkedin.com/in/vaibsharma86
github.com/Nutricalboii
```

---

## 10. What NOT to Build (explicit scope cuts)

- No fabricated "psychological profile" sections, no invented backstory about music/books/scents you haven't actually told an AI about — if you want those in your About page, write them yourself; don't let a model invent them.
- No fake filesystem content in the terminal easter egg — every path should resolve to something real.
- No Vaultflow presented as a finished product — it's a real ambition, label it as one.
- No autoplay audio, no "typing animation" intros, no 3D hero scenes unless you specifically want to build one and can justify why (e.g., if it demonstrates a real skill like Three.js you want to showcase).

---

## Notes for Antigravity IDE hand-off

Feed this file directly as a PRD-style content spec, phased like your other Avora work:
- **Phase 1:** site shell, hero, about, contact, 3 case studies (Vaelix OS, LOQ Control Center, ScholarSync — your most visually demonstrable and most "finished" projects).
- **Phase 2:** remaining case studies, terminal easter egg (4–5 real commands).
- **Phase 3:** polish pass — motion timing, responsive/mobile, performance.

Stack: Next.js 14, React 19, TypeScript, Tailwind, Vercel — consistent with everything else you build.
