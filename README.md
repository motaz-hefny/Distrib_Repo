# MoTekLab Universal Distribution Hub

Welcome to the public distribution repository for **MoTekLab** software projects, packages, installers, and release channels.

This repository serves as a centralized, organized release hub for all MoTekLab tools. Each project features its own dedicated subdirectory containing documentation, release notes, version manifests (`latest.json`), and direct binary download links.

Explore the full ecosystem at **[www.moteklab.com/products](https://www.moteklab.com/products)** and read engineering deep dives on the **[MoTekLab Journal](https://www.moteklab.com/blog)**.

---

## Software Catalog & Official Guides

| Project | Subfolder / Specs | Latest Release | Category | Live App / Official Guide |
|---|---|---|---|---|
| **MoTekLab MetaForge** | [`metaforge/`](metaforge/README.md) | `v0.10.2` | Media Tagging & Organization | [Product Page](https://www.moteklab.com/metaforge) · [Complete Guide](https://www.moteklab.com/blog/moteklab-metaforge-complete-guide) |
| **MoTekLab Proxy Suite** | [`proxy-suite/`](proxy-suite/README.md) | `v1.7.1` | Network Diagnostics & QA | [Release Guide](https://www.moteklab.com/blog/moteklab-proxy-suite-release) · [Downloads](https://www.moteklab.com/download/proxy-suite) |
| **MoTekLab Video Converter (`vconv`)** | [`vconv/`](vconv/README.md) | `v1.0.0` | Video Encoding & Remuxing | [v10 Architecture Guide](https://www.moteklab.com/blog/vconv-10-launch) · [Products](https://www.moteklab.com/products) |
| **MoTekLab VCEX Converter** | [`vcex-converter/`](vcex-converter/README.md) | `v1.2.0` | Certification & Exam Tooling | [Release Notes & Downloads](vcex-converter/README.md) |
| **MoTekLab Markdown Converter** | [`markdown-converter/`](markdown-converter/README.md) | `v1.1.0` | Document Formatting & Export | [Launch Web App](https://md.moteklab.com) · [RTF & Arabic RTL Guide](https://www.moteklab.com/blog/md-converter-rtf-images-arabic-rtl-privacy-guide) |
| **Fahhim AI Prompt Engineer** | Web & PWA | Live | Arabic/English Prompt Studio | [Launch Fahhim](https://fahhim.moteklab.com) · [Case Study](https://www.moteklab.com/blog/human-ai-synergy-scaling-fahhim-case-study) |

---

## Quick Install: MoTekLab MetaForge

### APT Repository (Debian / Ubuntu / Mint / Pop!_OS)

```bash
# Add official repository
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list

# Update & install
sudo apt update
sudo apt install moteklab-metaforge
```

### Direct Package Downloads

Binaries are attached directly to each release on GitHub:
- **[Browse All Releases & Assets](https://github.com/motaz-hefny/Distrib_Repo/releases)**
- Supported formats: `.deb` (Debian/Ubuntu), `.rpm` (Fedora/RHEL), `.AppImage` (Universal Linux). *(Windows installer support coming soon)*.

---

## Repository Layout

```
Distrib_Repo/
├── metaforge/                 # MoTekLab MetaForge
│   ├── README.md              # Detailed release notes, install steps & spec
│   ├── latest.json            # Version manifest & changelog
│   └── moteklab-metaforge.list # APT source entry
├── proxy-suite/               # MoTekLab Proxy Suite
│   ├── README.md              # Documentation & downloads
│   └── latest.json            # Version manifest
├── vconv/                     # Video Converter
│   ├── README.md              # Documentation & downloads
│   └── latest.json            # Version manifest
├── vcex-converter/            # VCEX Certification Studio
│   ├── README.md              # Documentation & downloads
│   └── latest.json            # Version manifest
├── markdown-converter/        # Markdown to Rich Text
│   ├── README.md              # Documentation & downloads
│   └── latest.json            # Version manifest
├── debian/                    # APT Pool & Dists (served via GitHub Pages)
├── latest.json                # Master multi-project version manifest
└── index.html                 # Web portal index
```

---

## Security & Privacy

MoTekLab applications are built with strict privacy standards:
- **Zero Embedded Credentials:** Never hardcodes developer tokens or secrets.
- **Keyless Default APIs:** Uses open Wikidata, Wikipedia, TVmaze, and Elcinema engines.
- **Local-First Execution:** All tagging, remuxing, and file manipulations happen entirely on your machine.
- **No Cloud Telemetry:** No tracking, usage analytics, or remote logging.

---

© 2026 [MoTekLab](https://www.moteklab.com). All rights reserved.
