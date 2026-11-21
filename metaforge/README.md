# MoTekLab MetaForge — Universal Distribution & Updates

[![Latest Release](https://img.shields.io/badge/release-v0.10.2-rose.svg)](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.2)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://moteklab.com)
[![Platform: Linux](https://img.shields.io/badge/platform-Linux-orange.svg)](#installation-options)

**MoTekLab MetaForge** is a free, privacy-first, lightweight Linux-native media metadata tagger and library organizer built with **Tauri v2**, **Rust**, and **Svelte 5**. Inspired by tools like MetaX, it inspects, fetches, edits, embeds, and renames movies, TV series, and personal video archives completely locally—without mandatory account registrations, hardcoded developer keys, or cloud telemetry.

---

## What's New in v0.10.2 & v0.10.1

- **In-App Release Update Center & Startup Notification (v0.10.2):** Built-in background update check on launch that highlights the **About** button with a notification dot whenever a newer release is published, plus a manual **Check for Updates** button with live status, direct release notes link, and a 1-click copy button for `sudo apt update && sudo apt upgrade`.
- **Fuzzy Typo Tolerance & Punctuation Invariance (v0.10.1):** Bounded Damerau-Levenshtein fuzzy matching and alphanumeric token normalization automatically bridge minor typos, missing apostrophes, hyphens, and dotted acronyms (e.g., `Greys Anatomy` matches `Grey's Anatomy`, `Spiderman` matches `Spider-Man`, `Agents of SHIELD` matches `Marvel's Agents of S.H.I.E.L.D.`), while keeping short words strict to prevent false matches.
- **Two-Tier TV Series Year Matching (v0.10.1):** Intelligently distinguishes between reboots sharing a name (strictly filtering *Dark Matter 2024* from *Dark Matter 2015* when a premiere year matches `target ± 1`) and long-running series (preserving *Grey's Anatomy 2005* even when an episode file is dated `2026`).
- **OMDb Apostrophe Fallback & Wikipedia Latency Cut (v0.10.1):** Automatic possessive retry for OMDb queries missing apostrophes, and Arabic Wikipedia queries are skipped on non-Arabic searches to cut latency and avoid rate limits.

## Core Highlights from v0.10.0

- **Instant In-Place Atomic MP4 Tagging:** Native `mp4ameta` in-place atomic atom writing for `.mp4` and `.m4v` files—tag multi-gigabyte videos in milliseconds without remuxing or copying the entire file on disk.
- **Media Server `.nfo` XML Exporter (Kodi / Jellyfin / Emby):** Standards-compliant `<movie>` and `<episodedetails>` XML `.nfo` generation with full cast, crew, studios, genres, plots, and unique ID cross-references (`imdb`, `tmdb`, `tvdb`), on-demand or automatically on write.
- **Concurrent Multi-Source Search Engine:** Parallel query execution via `futures::future::join_all`, reducing multi-provider search latency by ~85%.
- **Enhanced TV Filename & Folder Parser:** Automatically extracts show title, release year, season, and episode from complex filenames and parent folder names (e.g., `Arcane (2021)/...`).
- **Strict Movie vs. TV Isolation:** Prevents TV series results from polluting movie searches and vice-versa across Wikipedia, Wikidata, and TMDB.
- **Chapter Management & Interval Generator:** Read, edit, import (XML/sidecar), fetch from Apple Chapters & ChapterDB, detect scenes, or auto-generate evenly spaced "Every X min" chapters.
- **Batch Queue & Smart File Renaming:** Multi-select queue with per-file Movie/TV badges, batch rename overrides (`AUTO`, `ON`, `OFF`), and customizable naming templates.
- **Title Localization & Full Arabic / RTL Support:** Toggle between English and Original Title as the primary tag, with `<bdi>` bidirectional text isolation and a dual-language (English / Arabic) built-in help viewer.
- **Hot-Reload API Keys & Local Keychain Security:** Zero hardcoded developer keys; optional user keys reload instantaneously without restarting the app.

---

## Installation Options

### 1. APT Repository (Recommended — Debian / Ubuntu / Linux Mint / Pop!_OS)

Add the official MoTekLab distribution repository for seamless installation and automatic updates:

```bash
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list
sudo apt update
sudo apt install moteklab-metaforge
```

To upgrade whenever a new version is released:

```bash
sudo apt update && sudo apt upgrade moteklab-metaforge
```

### 2. Standalone Package Downloads

All binaries are published directly on the [MoTekLab Releases Page](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.2):

| Package Format | Target Operating System | Installation Command |
|---|---|---|
| **`.deb`** | Ubuntu / Debian / Mint (amd64) | `sudo dpkg -i moteklab_metaforge_0.10.2_amd64.deb` |
| **`.rpm`** | Fedora / RHEL / openSUSE (x86_64) | `sudo rpm -i moteklab_metaforge-0.10.2-1.x86_64.rpm` |
| **`.AppImage`** | Universal Linux (x86_64) | `chmod +x moteklab_metaforge_0.10.2_amd64.AppImage && ./moteklab_metaforge_0.10.2_amd64.AppImage` |

---

## Metadata Engines Supported

MetaForge provides keyless out-of-the-box querying without requiring any user registration:
- **Wikidata & Wikipedia REST API** (Keyless, global & multilingual)
- **TVmaze** (Keyless TV show and episode-level metadata)
- **Elcinema.com** (Keyless Arabic cinema & TV series engine)
- **Apple TV / iTunes** (Keyless catalog & high-resolution artwork)
- **TheMovieDB (TMDB)** (Optional user API key)
- **TheTVDB (TVDB v4)** (Optional user API key)
- **OMDb / IMDb** (Optional user API key)
- **Apple Chapters & ChapterDB** (Automated chapter mark lookups)

---

## Quick Links

- [Distribution Hub Main Index](../README.md)
- [Download Latest Binaries (v0.10.2)](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.2)
- [Official Website & Guides (MoTekLab)](https://www.moteklab.com)
- [MetaForge Download Portal](https://www.moteklab.com/download/metaforge)
