# MoTekLab Distribution Hub

Public release directory for all MoTekLab applications.

## Quick Install (MetaForge)

**APT (Debian / Ubuntu):**
```bash
echo "deb [trusted=yes] https://motaz-hefny.github.io/Distrib_Repo/debian stable main" | sudo tee /etc/apt/sources.list.d/moteklab-metaforge.list
sudo apt update
sudo apt install moteklab-metaforge
```

**Manual download:**
```bash
# Debian / Ubuntu
dpkg -i MoTekLab.MetaForge_*.deb

# Fedora / RHEL
rpm -ivh MoTekLab.MetaForge_*.rpm
```

## Projects

| Project | Latest | Description |
|---------|--------|-------------|
| [MetaForge](metaforge/) | [v0.3.2](metaforge/latest.json) | Free, private, Linux-first media metadata tagger |
| [Proxy Suite](proxy-suite/) | [latest](proxy-suite/latest.json) | Proxy harvesting, validation, and management suite |

## Repository Architecture

```
Distrib_Repo/
├── metaforge/
│   ├── latest.json          # MetaForge release metadata
│   └── moteklab-metaforge.list  # APT source entry (for reference)
├── proxy-suite/
│   └── latest.json          # Proxy Suite release metadata (coming soon)
├── latest.json              # Root index (all projects)
└── README.md                # ← You are here
```

## APT Repository (MetaForge only)

The APT repo is hosted via GitHub Pages and serves stable releases:

- **URL:** `https://motaz-hefny.github.io/Distrib_Repo/`
- **Suite:** `debian stable main`
- **Architecture:** `amd64`
- **Signing:** Unsigned — use `[trusted=yes]` in sources.list

### How it works

1. When a new release is published, the [update-repo](.github/workflows/update-repo.yml) workflow:
   - Downloads the `.deb` from the GitHub Release
   - Generates `Packages.gz` and `Release` files
   - Pushes to the `gh-pages` branch
2. Users run `sudo apt update` to get the latest index
3. `sudo apt install moteklab-metaforge` installs or upgrades

### RPM note

RPM packages are distributed via GitHub Releases only (no RPM repo server yet).
