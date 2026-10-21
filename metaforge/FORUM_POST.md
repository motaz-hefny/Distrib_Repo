# [ANN] MoTekLab MetaForge v0.10.0 Released — Instant MP4 Tagging, Kodi/Jellyfin NFO Exporter & Smart TV Parser

**Release Date:** October 21, 2026  
**Version:** v0.10.0  
**Repository:** [github.com/motaz-hefny/MoTekLab-MetaForge](https://github.com/motaz-hefny/MoTekLab-MetaForge)  
**Distribution Hub:** [github.com/motaz-hefny/Distrib_Repo](https://github.com/motaz-hefny/Distrib_Repo)  
**Website:** [moteklab.com](https://moteklab.com)

---

Hey everyone! 👋

We are thrilled to officially announce the release of **MoTekLab MetaForge v0.10.0** — our biggest and most comprehensive update to date.

For those new to the project, **MoTekLab MetaForge** is a free, lightweight, privacy-first media metadata tagger and organizer. It is designed to inspect, scrape, tag, embed covers, and organize movies, TV shows, and anime without locking you behind subscriptions, cloud telemetry, or mandatory API keys.

This milestone release addresses major community feature requests, overhauls the tagging engine for blazing-fast performance, integrates seamless export for home media servers (Kodi, Jellyfin, Emby, Plex), and vastly improves search and parsing accuracy.

Here is a full breakdown of everything new in **v0.10.0**:

---

## 🚀 What's New in v0.10.0

### 1. Instant In-Place Atomic MP4 Tagging (No More Slow File Copying!)
- **Previous limitation:** Tagging `.mp4` and `.m4v` video files previously relied on an `ffmpeg -c copy` disk remuxing pass. When tagging a 5GB or 15GB 4K file, this required copying the entire video stream to a temporary file on disk, leading to noticeable delays and heavy disk I/O.
- **v0.10.0 Solution:** We integrated native atomic in-place atom manipulation powered by `mp4ameta`. Standard iTunes/Apple atoms (`©nam`, `©alb`, `©ART`, `©day`, `tvsh`, `tvsn`, `tven`), custom freeform reverse-DNS tags (`com.apple.iTunes:DIRECTOR`, `WRITER`, `ORIGINAL_TITLE`), and high-resolution cover artwork are now written directly and atomically to the MP4 file header in milliseconds — identical to our instantaneous MKV tagging speed!

### 2. Media Server Integration: Kodi / Jellyfin / Emby XML `.nfo` Exporter
- Tagging your media is great, but local media servers (Kodi, Jellyfin, Emby, Plex) often rely on companion `.nfo` XML metadata files for instant indexing and offline artwork binding.
- MetaForge v0.10.0 introduces a dedicated NFO generation engine supporting both `<movie>` and `<episodedetails>` schemas:
  - Generates clean, XML-escaped tags: `<title>`, `<showtitle>`, `<season>`, `<episode>`, `<year>`, `<plot>`, `<outline>`, `<director>`, `<credits>` (writers), `<studio>`, `<genre>`, and `<actor><name>`.
  - Embeds unique provider identifiers (`<uniqueid type="imdb">`, `tmdb`, `tvdb`) to guarantee 100% scraper accuracy on your media server.
  - **On-Demand or Automated:** Use the new **"Export .nfo"** button in the editor toolbar whenever you want a quick sidecar file, or enable `"Automatically export .nfo metadata file when writing tags"` in Preferences to write them simultaneously with video tags!

### 3. Smart TV Filename Parser & Parent Directory Discovery
- Community filenames come in all shapes and sizes: `Arcane (2021) - S01E01.mp4`, `Avatar.The.Last.Airbender.2024.S02E01.1080p.mkv`, or folders containing clean episode files like `01 - Welcome to the Playground.mp4`.
- The new filename parser scans for `SxxExx` tokens across all delimited parts first, separating the show title, release year, season, and episode.
- If the file itself lacks a release year, MetaForge inspects the parent and ancestor directory names (e.g. `Arcane (2021)/Season 1/`) to auto-populate the year field!

### 4. Flexible ±1-Year Release Date Search Buffer
- In media databases, a show or movie might be indexed under 2023 in Wikidata but 2024 in TMDB or TVmaze depending on festival vs. theatrical vs. streaming release dates.
- MetaForge v0.10.0 introduces a flexible release year tolerance buffer: if you query with year `2024`, it intelligently evaluates `2023`, `2024`, and `2025`, prioritizing exact matches while ensuring you never get an empty search result over a minor calendar discrepancy.

### 5. Strict Media Type Isolation (Movies vs. TV Shows)
- Previously, ambiguous search terms could pull TV series into a movie search or vice-versa.
- We added heuristic categorizers to our open Wikidata and Wikipedia parsers. Searches flagged as `Movie` strictly filter out TV episodes and series, and `TV` searches reject standalone feature films.

### 6. Full Application State Reset
- Fixed an edge-case where resetting the application after tagging an 8-episode show would leave residual episode counters or rename override flags when loading a subsequent show.
- The **Reset** button now performs a deep, comprehensive memory wipe, clearing queue selections, rename overrides, media types, episode maps, and custom cover states.

### 7. Multi-Select Queue Batch Controls
- When working with full seasons or movie franchises, you can now select multiple files in the left-hand queue and toggle rename modes (`AUTO`, `ON`, `OFF`) across all selected items with a single click.

### 8. Interval Chapter Generator
- In the Chapters tab, a new **"Every X min"** generator allows you to create evenly spaced chapter marks across long-form video files, concert recordings, or educational lectures.

### 9. Modern Dark Brand Palette (Rose & Ember)
- The user interface has been restyled to reflect the official **MoTekLab brand aesthetic** (`moteklab.com`): deep slate backgrounds, elegant borders, crisp typography, and rose/amber accent highlights.

### 10. First-Class Arabic & Multilingual RTL Support
- Native `<bdi>` (bidirectional isolation) prevents mixed Arabic movie titles and English numbers/codecs from flipping or corrupting visual layout.
- Integrated dual-language documentation (English & Arabic) accessible via a one-click toggle in the integrated Help Viewer.

---

## 📖 Complete Application Guide: Everything You Need to Know About MetaForge

Whether you are tagging your very first movie or managing thousands of television episodes across an array of NAS storage servers, here is an exhaustive architectural and operational tour of how **MoTekLab MetaForge** works:

### 1. The Core Architecture & Philosophy
- **Rust Backend + Tauri v2:** MetaForge is powered by a high-efficiency Rust core running asynchronously on `tokio`. System calls are non-blocking, memory safety is enforced by the compiler, and resource consumption is a fraction of Electron-based tools.
- **Svelte 5 Frontend:** The user interface is crafted using modern Svelte 5 Runes (`$state`, `$derived`, `$effect`), providing instantaneous UI responsiveness without virtual DOM overhead.
- **Zero Telemetry & Local Execution:** There are no background phone-home analytics, user tracking IDs, or remote database synchronizations. Your files and file paths never leave your workstation.

### 2. Supported Formats & Native In-Place Tagging
MetaForge directly modifies file container atoms without requiring full file re-encoding or transcoding:
- **Matroska Containers (`.mkv`):** Uses an asynchronous `mkvpropedit` engine. Tags (Title, Year, Synopsis, Cast, Director, Studio, Genres, Original Title, Multi-language titles) and high-resolution cover attachments (with VLC-compatible attachment UIDs) are written directly into the Matroska header in milliseconds.
- **MPEG-4 Containers (`.mp4`, `.m4v`, `.m4a`):** Uses native atomic atom manipulation (`mp4ameta`). It modifies iTunes atoms (`©nam`, `©day`, `©alb`, `tvsh`, `tvsn`, `tven`, `covr`) and reverse-DNS custom atoms (`com.apple.iTunes:DIRECTOR`, `WRITER`, `ORIGINAL_TITLE`) in-place.
- **Companion XML (`.nfo`):** Standard Kodi, Jellyfin, and Emby XML metadata sidecars can be created on-demand or exported automatically alongside the media file.

### 3. Keyless & Extensible Scraping Engines
Unlike tools that lock you out until you sign up for external developer API keys, MetaForge is functional right out of the box with zero configuration:
- **Wikidata SPARQL:** Keyless, multilingual semantic queries for global films, directors, cast, release dates, and production entities.
- **Wikipedia REST API:** Summaries, infobox credits, and localized titles.
- **TVmaze REST API:** Keyless TV series and episode-by-episode metadata, including production codes and episode thumbnails.
- **Elcinema.com:** Dedicated keyless Middle Eastern and Arabic film, TV, and theater scraper.
- **Optional API Keys:** If you own API keys for **TheMovieDB (TMDB)**, **TheTVDB (TVDB v4)**, or **OMDb / IMDb**, you can add them in Preferences under the API Keys tab. They hot-reload immediately into memory without requiring an app restart.

### 4. Arabic Typography & RTL Bidirectional Safety
Mixed text (such as Arabic film titles combined with English numbers, resolutions like `1080p`, or audio codec names) notoriously wrecks layout in standard LTR user interfaces. MetaForge solves this natively:
- Mixed-direction fields are isolated inside `<bdi>` (bidirectional isolation) HTML elements.
- The interface enforces `unicode-bidi: isolate;` and `direction: ltr;` rules on technical cells to guarantee text flow never breaks.
- Full dual-language documentation (English & Arabic) is built into the help viewer with an instant toggle.

### 5. Smart Renaming & Directory Organization
MetaForge includes an automated template engine for organizing your disks:
- **Movie Templates:** Default `{title} ({year})`
- **TV Show Templates:** Default `{show} - S{season:02}E{episode:02} - {title}`
- **Article Moving:** Supports `{folder_title}` token to automatically format folders cleanly (e.g. `Matrix, The` or `The Matrix`).
- **Batch Override Controls:** Each queued file or selected batch can be set to `AUTO`, forced `ON`, or disabled `OFF`.

### 6. Built-in Chapter Editor & Importers
- **Online Chapter Lookup:** Scrapes chapter marks directly from Apple iTunes and ChapterDB.
- **Interval Generator:** Create custom chapter markers every $X$ minutes for lengthy videos or home recordings.
- **Manual Editor:** Adjust timestamps, rename chapter names, and preview boundaries.

---

## 📥 How to Install & Upgrade

### Debian / Ubuntu / Linux Mint / Pop!_OS (APT Repository)

Add the MoTekLab Distribution repository for seamless automatic updates:

```bash
# 1. Register repository
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list

# 2. Update and install
sudo apt update
sudo apt install moteklab-metaforge
```

### Standalone Downloads

Pre-built binaries are available on the [MoTekLab Distribution Hub Releases](https://github.com/motaz-hefny/Distrib_Repo/releases/tag/v0.10.0):
- **Debian / Ubuntu package:** `moteklab_metaforge_0.10.0_amd64.deb`
- **Fedora / RHEL / openSUSE RPM:** `moteklab_metaforge-0.10.0-1.x86_64.rpm`
- **Universal Linux:** `moteklab_metaforge_0.10.0_amd64.AppImage`
- **Windows x64:** Portable and installer packages (`.exe` / `.msi`)

---

## 🔒 Security & Privacy Notice

MoTekLab MetaForge operates under a zero-telemetry, zero-compromise security posture:
- **Zero Embedded Credentials:** No hardcoded developer keys or tracking tokens.
- **Keyless Default Querying:** Instant access to Wikipedia, Wikidata, TVmaze, and Elcinema without signing up or creating developer accounts.
- **Local Isolation:** All operations happen entirely within your local environment.

---

## 💬 Community Feedback & Discussion

We'd love to hear your thoughts, test results, and feature suggestions! Let us know how v0.10.0 works on your media library in the replies below or on our community portal at [moteklab.com](https://moteklab.com).

Happy tagging! 🍿
