# MoTekLab MetaForge — Universal Distribution & Updates

[![Latest Release](https://img.shields.io/badge/release-v0.10.0-rose.svg)](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.0)
[![License: Proprietary](https://img.shields.io/badge/license-Proprietary-blue.svg)](https://moteklab.com)
[![Platform: Linux](https://img.shields.io/badge/platform-Linux-orange.svg)](#installation)

**MoTekLab MetaForge** is a fast, privacy-first, lightweight media metadata tagger and organizer. Inspired by tools like MetaX, it operates completely locally without mandatory account registrations, third-party analytics, or telemetry.

---

## What's New in v0.10.0

- ⚡ **Instant In-Place Atomic MP4 Tagging:** Replaced slow disk-copying remux routines with native `mp4ameta` in-place atomic atom manipulation. Gigabyte-sized `.mp4` and `.m4v` movies and series tag instantaneously without burning disk I/O.
- 📺 **Media Server Integration (Kodi / Jellyfin / Emby XML `.nfo` Exporter):** Standard XML `.nfo` generation (`<movie>` and `<episodedetails>` schemas) with XML-escaped titles, show titles, year, season, episode, plots, directors, writers, studios, genres, actors, and unique ID cross-references (`imdb`, `tmdb`, `tvdb`). Automatically exports alongside media files on write, or on-demand via the "Export .nfo" button.
- 🎯 **Enhanced TV Filename Parser:** Intelligently extracts show title, release year, season, and episode from complex filenames with dot or dash delimiters and ancestor folder names (e.g. `Arcane (2021)/...`, `Avatar.The.Last.Airbender.2024.S02E01...`).
- 🛡️ **Flexible Year Tolerance Buffer (±1 Year):** Prevents search failures caused by slight discrepancy in release year listings (e.g., searching 2024 checks 2023–2025) while strictly prioritizing exact matches.
- 🎬 **Strict Media Type Separation:** Heuristically isolates Wikipedia, Wikidata, and TMDB hits into `Movie` or `TV` types so TV episodes never pollute Movie lookups.
- 🧹 **Full Application State Reset:** Thorough state hygiene resets queue selection, media types, rename overrides, and cached field data across searches.
- 📋 **Batch Queue Controls:** Toggle rename rules (`AUTO`, `ON`, `OFF`) across multi-selected items simultaneously.
- ⏱️ **Interval Chapter Generator:** Automatic "Every X min" chapter maker for long videos, lectures, and home movies.
- 🎨 **MoTekLab Brand Styling:** Polished Rose & Ember dark theme aligned with `https://moteklab.com`.
- 🌐 **Arabic & RTL Precision:** Full `<bdi>` bidirectional text isolation and dual-language help (English & Arabic).

---

## Installation Options

### 1. APT Repository (Debian / Ubuntu / Linux Mint / Pop!_OS)

Add the official MoTekLab distribution repository for automatic updates:

```bash
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list
sudo apt update
sudo apt install moteklab-metaforge
```

To update when a new version is released:
```bash
sudo apt update && sudo apt upgrade moteklab-metaforge
```

### 2. Standalone Package Downloads

All binaries are available on the [MoTekLab Releases Page](https://github.com/motaz-hefny/Distrib_Repo/releases):

| Package Format | Target Operating System | Installation Command / Note |
|---|---|---|
| **`.deb`** | Ubuntu / Debian / Mint (amd64) | `sudo dpkg -i moteklab_metaforge_0.10.0_amd64.deb` |
| **`.rpm`** | Fedora / RHEL / openSUSE | `sudo rpm -i moteklab_metaforge-0.10.0-1.x86_64.rpm` |
| **`.AppImage`** | Universal Linux | `chmod +x moteklab_metaforge_0.10.0_amd64.AppImage && ./moteklab_metaforge_0.10.0_amd64.AppImage` |
| **`.exe` / `.msi`** | Windows (x64) | *(Coming Soon)* Standalone Windows installer and portable archive |

---

## Metadata Engines Supported

MetaForge provides keyless out-of-the-box querying without requiring any user registration:
- **Wikidata & Wikipedia REST API** (Keyless, global & multilingual)
- **TVmaze** (Keyless TV show and episode-level metadata)
- **Elcinema.com** (Keyless Arabic cinema & TV series engine)
- **TheMovieDB (TMDB)** (Optional user API key)
- **TheTVDB (TVDB v4)** (Optional user API key)
- **OMDb / IMDb** (Optional user API key)
- **Apple Chapters & ChapterDB** (Automated chapter mark lookups)

---

## Quick Links

- [Distribution Hub Main Index](../README.md)
- [Download Latest Binaries](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.0)
- [Official Website](https://moteklab.com)
