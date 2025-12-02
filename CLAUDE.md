# Octa Releases - Claude Context

> **Related Contexts:**
> - Source code & full docs: `octa/CLAUDE.md` in `techyowls-branding` repo
> - Brand-wide context: `techyowls-branding/CLAUDE.md`

---

## Overview

This is the **public releases repository** for Octa. It contains:
- Binary releases (DMG, MSI, DEB files)
- Screenshots for README
- Public-facing documentation

**Source code is in the private `octa` repo.**

---

## Repository Purpose

| Repo | Visibility | Purpose |
|------|------------|---------|
| `Moshiour027/octa` | Private | Source code, GitHub Actions |
| `Moshiour027/octa-releases` | **Public** | Binary downloads, screenshots |

---

## How Releases Get Here

### Option 1: Full CI (GitHub Actions)
When you push a tag to `octa`, GitHub Actions automatically:
1. Builds all platforms (macOS, Windows, Linux)
2. Creates a release in this repo
3. Uploads all binaries

### Option 2: Hybrid Build (RECOMMENDED - saves CI minutes)

macOS builds cost 10x more CI minutes. Build locally instead:

```bash
# 1. In octa repo: push tag (builds Windows + Linux via CI)
git tag v0.1.2 && git push origin v0.1.2

# 2. Build macOS locally
npm run tauri build

# 3. Upload local DMGs to this repo
gh release upload v0.1.2 \
  src-tauri/target/release/bundle/dmg/Octa_0.1.2_aarch64.dmg \
  src-tauri/target/release/bundle/dmg/Octa_0.1.2_x64.dmg \
  --repo Moshiour027/octa-releases
```

### Option 3: Manual Upload via Web UI
1. Go to Releases → Edit release
2. Drag & drop DMG/MSI/DEB files
3. Save

---

## Updating This Repo Manually

```bash
# Clone fresh
git clone git@github.com:Moshiour027/octa-releases.git /tmp/octa-releases
cd /tmp/octa-releases

# Make changes (update README, add screenshots, etc.)
git add .
git commit -m "Update for vX.Y.Z"
git push
```

---

## Download URLs

All downloads use GitHub's release system:

```
https://github.com/Moshiour027/octa-releases/releases/latest/download/{filename}
```

| Platform | Filename Pattern |
|----------|------------------|
| macOS ARM | `Octa_{version}_aarch64.dmg` |
| macOS Intel | `Octa_{version}_x64.dmg` |
| Windows | `Octa_{version}_x64_en-US.msi` |
| Linux | `Octa_{version}_amd64.deb` |

---

## Screenshots

Location: `screenshots/`

To update:
1. Take new screenshots
2. Add to `screenshots/` folder
3. Update `README.md` image references
4. Commit and push

---

## Links

| Resource | URL |
|----------|-----|
| Source Code (private) | https://github.com/Moshiour027/octa |
| Landing Page | https://octa.techyowls.io |
| Purchase | https://techyowls.lemonsqueezy.com/buy/90f03bd0-7801-4aa1-bfb9-e24ebdac4185 |

---

*Last updated: December 2, 2025*
