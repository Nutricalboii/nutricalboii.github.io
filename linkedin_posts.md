# LinkedIn Posts & Activity Archive

Archive of professional posts, updates, and articles shared on LinkedIn by Vaibhav Sharma.

---

## Post 1: Open Source & Late-Night Engineering (SMASH for Linux)
**Date:** ~June 2026

724 GitHub contributions done.
The green squares were what got me started.
At first, it was just about keeping the graph alive. Somewhere along the way, it became about building things simply because I couldn't stop thinking about them.

This year involved:
- Participating in Google & Meta hackathons
- Building and deploying projects
- Maintaining repositories, PRs, and merges
- Developing **VaelixOS** (an Ubuntu-based OS for laptops), working on an **Android 13 port for the Moto G5 Plus**, bringing **Ubuntu Touch** to the same device, and creating a few **Magisk modules**.

### Featured Project: SMASH for Linux
One of them came from seeing a reel where a Mac played a sound whenever someone hit it. Naturally, I wondered, "Why should macOS have all the fun?" So I built **SMASH for Ubuntu/Linux** — a utility that listens for the sound signature of someone physically smacking their laptop and plays a reaction sound while ignoring speech and background noise. Depending on the audio assets provided, the reactions can range from perfectly normal to completely chaotic, which is exactly the kind of thing a bored engineer ends up building at 2 AM.

A completely unnecessary project, which is precisely why I built it.
You can find it on my GitHub under the **SMASH** repository.

> I use AI tools quite a lot — they're great for speeding up development, exploring ideas, and getting unstuck. But AI never sat through failed builds, spent hours reading logs, or kept trying after the nineteenth approach failed. The ideas were mine, the curiosity was mine, and the learning was mine too. Looking back, these contributions didn't just make me a better developer; they made me more patient with problems, more comfortable with uncertainty, and less afraid of failure. The graph is green, but the real lessons were earned elsewhere.

---

## Post 2: CS50x HarvardX Graduation
**Date:** ~May 2026

Excited to share that I’ve successfully completed **CS50x: Introduction to Computer Science** through HarvardX / edX.

This journey was much more than learning syntax or writing code. It strengthened my understanding of computational thinking, problem-solving, algorithms, data structures, and the foundations behind how software systems are designed and built.

Through topics including C, Python, SQL, HTML/CSS/JavaScript, Flask, and Artificial Intelligence, one of the biggest takeaways for me was realizing that computer science is not only about creating software — it’s about learning how to think, break down complex problems, and build solutions with purpose.

---

## Post 3: LOQ Control Center v2.0 Release
**Date:** ~May 2026

Update: v2.0 dropped. It actually works now.
A few months ago I shared v1.0 — a production-hardened hardware orchestration layer for Lenovo LOQ on Linux.
I said "still testing." I meant it. Here's what broke, what I learned, and what I rebuilt.

### Architecture Fixes:
The v1.0 architecture had a fundamental flaw — it was writing directly to ACPI sysfs via `pkexec`, which meant every profile switch spawned an authentication prompt that hid behind the app window. Users couldn't see it. Hardware writes silently failed. The UI froze and never recovered.

That's not a UX bug. That's a trust violation. Fixed it at the root.

### What's new in v2.0:
- **Fedora-native power management:** Replaced raw sysfs writes with `powerprofilesctl`, which talks to `power-profiles-daemon` over D-Bus as a normal user. No `pkexec`. No auth prompt. Instant, reliable profile switching on both Fedora and Ubuntu.
- **4-profile system matching Lenovo LOQ hardware:** Blue (Quiet), White (Balanced), Red (Performance), and now Purple (Custom) — a full Lenovo Vantage-equivalent tuner built in. CPU PL1/PL2 via RAPL, GPU cTGP via `nvidia-smi`, GPU clock offsets via `nvidia-settings`, and an interactive fan curve editor with a Cairo-rendered 7-point graph and hardware safety floor enforcement.
- **Fn+Q keyboard sync:** Physical hardware profile changes now reflect in the GUI in real-time via a 1-second sysfs poll loop. No more stale UI.
- **GPU mode switching:** Integrated/Hybrid/NVIDIA via `envycontrol` with automatic fallback to `prime-select` depending on distro. Auto-detected. No hardcoding.
- **Thermal noise eliminated:** Rewrote the sensor stack to read directly from `/sys/class/hwmon` and RAPL energy counters instead of spawning sensors on every tick. Killed ~300 `temp1_max_alarm` stderr lines per minute.
- **UI state machine hardened:** The old `set_sensitive(False)` path had a race condition where any exception left the entire window permanently unclickable. Replaced with scoped per-operation sensitivity with guaranteed `finally` restoration.

---

## Post 4: Vaelix OS Booting Phase
**Date:** ~May 2026

Built the current basic structure of my custom Linux distribution: **Vaelix OS**.

After 13 builds / rebuilds, I finally got it booting cleanly to the home screen and running as a usable desktop. That moment hits different.

### What I’m Building:
A Linux OS focused on:
- **Professional feel** – premium visuals, polished UI, refined dark themes
- **Smooth experience** – fluid animations, responsive desktop, no unnecessary bloat
- **Battery intelligence** – optimized profiles for laptops and daily use
- **Performance modes** – full power when needed
- **Gaming Mode** – unlock max performance when enabled
- **Creator workflow** – fast, distraction-free productivity setup
- **Customization** – multiple atmospheres/themes in one system
- **Clean control center** – one place for tuning everything

### Current Stack / Base:
- Ubuntu 24.04 base
- KDE Plasma desktop
- Custom Vaelix Control Center
- XanMod kernel tuning
- Custom themes / UI identity

---

## Post 5: Android 13 Bring-Up on Potter
**Date:** ~April 2026

Bringing Android 13 to a device that was never meant to run it.
A few months back, I revisited my first Android phone — Moto G5 Plus (potter). Official support ended at Android 8.1. Community ROMs carried it till Android 11.

Currently working on a full **LineageOS 20 (Android 13)** bring-up on msm8953 — completely unsupported territory.

This is not a “repo sync + build” kind of setup. It turned into a full system reconstruction:
- Repairing a broken AOSP/Lineage tree (mixed branches, corrupted prebuilts)
- Understanding Soong/Ninja instead of bypassing it
- Rebuilding dependency graph without fake stubs
- Injecting missing AOSP components where Lineage manifests fall short
- Handling framework ↔ vendor ↔ kernel mismatch (3.18 kernel vs Android 13)
- Working through VINTF constraints for legacy hardware
- Starting kernel-side adaptations (binderfs absence, memfd gaps)
- Debugging at platform level instead of silencing errors

---

## Post 6: LOQ Control Center v1.0.0
**Date:** ~April 2026

Introducing: **LOQ Control Center v1.0.0** (Local Production-Hardened Build).

### Engineering Upgrades:
- **Proper Linux Security Model:** The application now runs as a normal user. Privileged hardware actions trigger native system authentication—no full-app sudo required.
- **Adaptive Performance Governor:** Built a background “brain” that analyzes workload and thermal trends, dynamically balancing performance, acoustics, and battery efficiency.
- **Production Stability Layer:** Centralized `StateManager` with transition locking, deadlock watchdog, and retry framework.
- **Custom High-Performance Telemetry Engine:** Native Cairo-based real-time graphs for power, temperature, and utilization tracking.
- **User Experience Evolution:** Intelligent fan hysteresis logic engineered to significantly reduce oscillation noise.

---

## Post 7: Switch to Linux & Hardware Reverse-Engineering
**Date:** ~April 2026

I switched to Linux and ended up reverse engineering my own laptop in two weeks.

On Windows everything felt polished and ready-made, but on Linux I suddenly lost direct control over my own hardware. That gap pushed me to explore kernel power layers, firmware behaviour, and hidden system interfaces.

What started as a small frustration quickly turned into a challenge — so instead of waiting for solutions, I started building **LOQ Control Center**.

---

## Post 8: Initiating LOQ Control Center Project
**Date:** ~April 2026

Switched my main laptop (Lenovo Loq) to Ubuntu. No dual boot. No safety net.
Loved the control, performance tuning, and the raw feel of owning the system.

But one thing was clearly missing — a proper hardware control center like Lenovo Vantage for my LOQ.
So instead of adjusting around the gap, I started building my own open-source control center for Lenovo LOQ laptops on Linux.

---

## Post 9: Telegram Affiliate Automation Bot
**Date:** ~April 2026

Revisiting one of my earlier projects — a Telegram Affiliate Automation Bot built while experimenting with messaging automation and API-driven systems.

### Dual-Runtime Setup:
- **Python (Telethon)** to handle the MTProto layer and message broadcasting.
- **Node.js** to manage ingestion, filtering, and link processing.
- Merchant URLs were converted to monetized links using the **Cuelinks API**.

---

## Post 10: Notum End-to-End Encryption Completed
**Date:** ~April 2026

Quick development update on **Notum** — the zero-knowledge memory vault I’ve been building.
Completed the end-to-end encrypted note flow. Notes are now encrypted locally on the client using AES-GCM before reaching the backend.

- Client-side encryption using **WebCrypto**
- Secure **Electron** client with **Fastify** backend
- JWT-based authentication with per-user encryption salts

---

## Post 11: Notum Desktop Client Inception
**Date:** ~March 2026

Notum desktop client foundation established.
- Built **Electron** desktop client base
- Implemented secure renderer isolation
- Sandboxed environment checks

---

## Post 12: Notum Zero-Knowledge Architecture
**Date:** ~March 2026

Transitioned Notum into a zero-knowledge storage model:
- AES-256-GCM encrypted storage model
- Rate-limited authentication rules
- Per-user encryption salts with deterministic key derivation

---

## Post 13: Notum Inception
**Date:** ~March 2026

Started building **Notum** — a private memory vault focused on privacy, ownership, and simplicity.
Following a local-first approach to ensure your data stays yours.

---

## Post 14: Full-Stack Developer Internship Completion
**Date:** ~February 2026

Completed a 1-month internship as a Full Stack Developer Intern at Codec Technologies Pvt. Ltd., under an AICTE & ICAC-approved program.

---

## Post 15: Sovereign Plate Luxury Portal Deployment
**Date:** ~January 2026

Successful deployment of **The Sovereign Plate**, a digital platform engineered for the premium hospitality sector.
- **Acrylic Aesthetic:** backdrop-filter styling & golden branding accents.
- **SMS notifications:** automated confirmation triggers via the **Twilio API**.
- **Dynamic Content:** managed dynamically using a **MongoDB** database.
- **Stack:** Netlify frontend, Node/Express backend on Render.

---

## Post 16: Commencing Codec Technologies Internship
**Date:** ~December 2025

Officially joined Codec Technologies as a Full Stack Developer Intern.

---

## Post 17: ADYA Advanced Desktop AI Assistant
**Date:** ~November 2025

Introducing **ADYA** — an advanced desktop AI assistant built with Python & PyQt5.
- Voice Recognition & Real-time TTS
- LLM-router architecture (Google Gemini & local models)
- Spotify API & system resource widget controls

---

## Post 18 & 19: Certifications
**Date:** ~November 2025

- **Complete HTML** (100% Score) certified by KnowledgeGate.
- **Mastery in JavaScript** certified by Lernx.
