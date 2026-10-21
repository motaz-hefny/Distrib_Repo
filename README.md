# MoTekLab Universal Distribution Hub

Welcome to the public distribution repository for **MoTekLab** software projects, packages, installers, and release channels.

This repository serves as a centralized, organized release hub for all MoTekLab tools. Each project features its own dedicated subdirectory containing documentation, release notes, version manifests (`latest.json`), and direct binary download links.

---

## 📦 Software Catalog & Projects

| Project | Subfolder / Specs | Latest Release | Category | Direct Download / Info |
|---|---|---|---|---|
| **MoTekLab MetaForge** | [`metaforge/`](metaforge/README.md) | `v0.10.0` | Media Tagging & Organization | [Release Notes & Downloads](metaforge/README.md) |
| **MoTekLab Proxy Suite** | [`proxy-suite/`](proxy-suite/README.md) | `v1.7.1` | Network Engineering & Scraping | [Release Notes & Downloads](proxy-suite/README.md) |
| **MoTekLab Video Converter (`vconv`)** | [`vconv/`](vconv/README.md) | `v1.0.0` | Video Encoding & Remuxing | [Release Notes & Downloads](vconv/README.md) |
| **MoTekLab VCEX Converter** | [`vcex-converter/`](vcex-converter/README.md) | `v1.2.0` | Certification & Exam Tooling | [Release Notes & Downloads](vcex-converter/README.md) |
| **MoTekLab Markdown Converter** | [`markdown-converter/`](markdown-converter/README.md) | `v1.1.0` | Document Formatting & Export | [Release Notes & Downloads](markdown-converter/README.md) |

---

## 🚀 Quick Install: MoTekLab MetaForge

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

## 📁 Repository Layout

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

## 🔒 Security & Privacy

MoTekLab applications are built with strict privacy standards:
- **Zero Embedded Credentials:** Never hardcodes developer tokens or secrets.
- **Keyless Default APIs:** Uses open Wikidata, Wikipedia, TVmaze, and Elcinema engines.
- **Local-First Execution:** All tagging, remuxing, and file manipulations happen entirely on your machine.
- **No Cloud Telemetry:** No tracking, usage analytics, or remote logging.

---

© 2026 [MoTekLab](https://moteklab.com). All rights reserved.
