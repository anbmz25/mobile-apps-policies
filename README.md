# mobile-apps-policies

Public repo for hosting privacy policies and other policy pages for mobile apps. Content is **Markdown** (`.md`); GitHub Pages uses Jekyll to render it to HTML.

## Setup (one-time)

1. **Create the repo on GitHub**
   - New repository: `mobile-apps-policies`
   - Owner: `anbmz25`
   - Public, no need to add README (this folder has the content)

2. **Clone and add this content**
   ```bash
   git clone git@github.com:anbmz25/mobile-apps-policies.git
   cd mobile-apps-policies
   # Copy the contents of the `mobile-apps-policies` folder from your parkingspot project:
   # - index.md (at repo root)
   # - confipark/privacy.md
   # Or, if you're in the parkingspot project:
   # cp -r mobile-apps-policies/* /path/to/mobile-apps-policies/
   git add .
   git commit -m "Add ConfiPark privacy policy"
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Repo → **Settings** → **Pages**
   - **Source:** Deploy from a branch
   - **Branch:** `main` / **Folder:** `/ (root)` → Save
   - After a minute, the site is live.

## URLs (after Pages is enabled)

| Page | URL |
|------|-----|
| Landing | https://anbmz25.github.io/mobile-apps-policies/ |
| **ConfiPark privacy (for Play Console)** | **https://anbmz25.github.io/mobile-apps-policies/confipark/privacy** |

## Syncing from parkingspot (automated)

From the **parkingspot** project root you can push updates to the policies repo with:

```bash
./scripts/sync-policies-repo.sh
```

Requires the policies repo cloned as a **sibling** of parkingspot (e.g. `../mobile-apps-policies`). Override path with:

```bash
POLICIES_REPO_PATH=/path/to/mobile-apps-policies ./scripts/sync-policies-repo.sh
```

## Adding another app later

Add a new folder, e.g. `otherapp/privacy.md`, and add a link on the root `index.md`. GitHub Pages (Jekyll) will render the Markdown to HTML.
