# MoTekLab Public Software Distribution Hub (`Distrib_Repo`)

![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20Web-0ea5e9) ![Privacy](https://img.shields.io/badge/Telemetry-Zero-10b981) ![Languages](https://img.shields.io/badge/Languages-English%20%2B%20Arabic%20RTL-6366f1) ![Releases](https://img.shields.io/github/v/release/motaz-hefny/Distrib_Repo?label=Latest%20Release)

## What Is This Repository?

**This is the official public release and package distribution hub for [MoTekLab](https://www.moteklab.com) applications.**

Some MoTekLab applications are open source (with their full code in dedicated public repositories), while others are **freeware whose source code repositories are kept private**. Regardless of whether an app's source code is public or private, **all official compiled Linux installers (`.deb`, `.rpm`, `.AppImage`), APT packages, version manifests, and release notes are published publicly here** so anyone can safely download, verify, and auto-update MoTekLab software.

- **Official Website & Product Suite:** [www.moteklab.com/products](https://www.moteklab.com/products)
- **Engineering Journal & Guides:** [www.moteklab.com/blog](https://www.moteklab.com/blog)
- **Direct Binary Releases:** [Browse All Releases & Installers](https://github.com/motaz-hefny/Distrib_Repo/releases)

---

## Applications Included in the MoTekLab Ecosystem

### 1. MoTekLab MetaForge (`v0.10.2`) — Linux Media Metadata Tagger
- **What it does:** Automatically discovers metadata, posters, cast credits, chapters, and Kodi/Jellyfin/Emby `.nfo` XML files for your local MKV, MP4, and M4V video libraries, then writes tags losslessly in-place without re-encoding.
- **Why use it:** Works out of the box with zero API keys (Wikipedia, Wikidata, TVmaze, Apple TV, Elcinema), supports optional local keychain keys (TMDB/TVDB/OMDb), isolates mixed Arabic/English BiDi titles cleanly, and runs 100% locally with zero telemetry.
- **Availability:** Freeware (private source repo; public `.deb`, `.rpm`, `.AppImage`, and APT repo hosted here).
- **Links:** [Product Page](https://www.moteklab.com/metaforge) · [Complete Guide](https://www.moteklab.com/blog/moteklab-metaforge-complete-guide) · [Download v0.10.2](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.2) · [Specs](metaforge/README.md)

### 2. MoTekLab Proxy Suite (`v2.6.3`) — Linux Multi-Hop Proxy Routing & Diagnostics
- **What it does:** A local-first Linux desktop utility for multi-hop SOCKS5/HTTP proxy chaining (Cascade mode), real-time latency and health telemetry, Judge verification, SSRF security hardening, and automated Chromium regional QA testing.
- **Why use it:** Gives developers and QA engineers full local control over proxy chains and network diagnostics without cloud relays or telemetry.
- **Availability:** Freeware (private source repo; public `.AppImage`, `.deb`, and `.tar.gz` binaries hosted here).
- **Links:** [Download Portal](https://www.moteklab.com/download/proxy-suite) · [Release Guide](https://www.moteklab.com/blog/moteklab-proxy-suite-release) · [Download v2.6.3](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v2.6.3) · [Specs](proxy-suite/README.md)

### 3. MoTekLab Video Encoder / `vconv` (`v10.0.5`) — Linux Hardware-Accelerated Video Converter
- **What it does:** A PyQt6 desktop GUI and headless CLI video converter powered by HandBrakeCLI featuring NVIDIA NVENC, Intel QSV, and AMD AMF hardware acceleration, VMAF/SSIM/PSNR visual fidelity grading, output size forecasting, strict MKV/MP4 metadata parity, and Arabic subtitle support.
- **Why use it:** Combines HandBrakeCLI reliability with quality-verified compression forecasting and zero telemetry.
- **Availability:** Free & Open Source (GPLv3) — full source code and releases live at [github.com/motaz-hefny/MoTekLab-vconv](https://github.com/motaz-hefny/MoTekLab-vconv) and mirrored on [SourceForge](https://sourceforge.net/projects/moteklab-vconv/).
- **Links:** [Architecture Guide](https://www.moteklab.com/blog/vconv-10-launch) · [GitHub Releases](https://github.com/motaz-hefny/MoTekLab-vconv/releases) · [Specs](vconv/README.md)

### 4. MoTekLab MD Converter Pro — Client-Side Markdown, Rich Text, RTF & Arabic RTL Workbench
- **What it does:** A 100% browser-native workbench for real-time bidirectional conversion between Markdown, Rich Text, RTF 1.5 (Word & Scrivener compatible with embedded PNG/JPEG images), HTML, and PDF—with live Mermaid SVG diagrams, KaTeX math, Burner Mode panic purge, and native Arabic RTL Word export.
- **Why use it:** Your documents never leave your browser—zero server uploads, zero accounts, zero tracking.
- **Availability:** Free Web App (no installation required).
- **Links:** [Launch md.moteklab.com](https://md.moteklab.com) · [RTF, Images & Arabic RTL Guide](https://www.moteklab.com/blog/md-converter-rtf-images-arabic-rtl-privacy-guide) · [Specs](markdown-converter/README.md)

### 5. Fahhim AI Prompt Engineer — Arabic & English Structured Prompt Studio
- **What it does:** Guides creators, developers, and teams through proven prompt frameworks (COSTAR, ICDF, RCR-EOC, MICRO) to generate high-precision prompts for ChatGPT, Claude, Gemini, and Llama, with native Arabic (MSA & Egyptian Masri) RTL support and local browser storage.
- **Availability:** Free Web App, PWA & Android.
- **Links:** [Launch fahhim.moteklab.com](https://fahhim.moteklab.com) · [Prompt Library](https://fahhim.moteklab.com/prompts) · [Case Study](https://www.moteklab.com/blog/human-ai-synergy-scaling-fahhim-case-study)

### 6. MoTekLab VCEX Converter (`v1.2.0`) — Certification & Exam Format Tooling
- **What it does:** High-fidelity exam format conversion, blueprint verification, and lossless JSON/VCEX roundtripping for certification study workflows.
- **Availability:** Freeware (private source repo; public specs and manifests in [`vcex-converter/`](vcex-converter/README.md)).

---

## Quick Install: MoTekLab MetaForge (APT Repository)

### Debian / Ubuntu / Linux Mint / Pop!_OS

```bash
# Add official MoTekLab APT repository
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list

# Update & install
sudo apt update
sudo apt install moteklab-metaforge
```

### Direct Package Downloads
- **[Browse All Releases & Binary Assets](https://github.com/motaz-hefny/Distrib_Repo/releases)**
- Supported Linux formats: `.deb` (Debian/Ubuntu), `.rpm` (Fedora/RHEL), `.AppImage` (Universal Linux).

---

## Security & Privacy Standards

Every MoTekLab application adheres to strict privacy guarantees:
- **Zero Embedded Credentials:** No hardcoded developer API keys or hidden tokens.
- **Local-First Execution:** Tagging, encoding, routing, and document conversion execute locally on your machine.
- **Zero Cloud Telemetry:** No behavioral tracking, analytics beacons, or remote document logging.

---

© 2026 [MoTekLab](https://www.moteklab.com). All rights reserved.
