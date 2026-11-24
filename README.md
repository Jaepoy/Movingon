# Moving On — 30-to-90-Day Transition Companion

A static, offline-capable PWA (no build step) for GitHub Pages.

## GitHub Upload Checklist

Put these 6 files in the **root** of a single repository:

- [ ] `index.html` — public landing & sales page
- [ ] `tracker.html` — the buyer tracker (home screen app)
- [ ] `manifest.json` — PWA configuration
- [ ] `sw.js` — service worker (offline support)
- [ ] `icon-192.png` — app icon
- [ ] `icon-512.png` — app icon

### Before you upload, edit
1. `index.html` → `CONFIG` block at the top: brand name, how you introduce yourself, price, contact handle and link.
2. `tracker.html` → `TRACKER_CONFIG` block at the top: `ACCESS_CODE` (default `HEAL2026`) or set `REQUIRE_CODE: false` to disable the gate.

### Enable GitHub Pages
1. Create a new repository and upload the 6 files (Add file → Upload files → Commit).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*.
4. Choose branch **main** and folder **/ (root)**, then **Save**.
5. Wait about a minute. Your site will be at `https://<username>.github.io/<repo>/`.
6. Buyers get: `https://<username>.github.io/<repo>/tracker.html` + the unlock code.

### Updating later
Change `CACHE_VERSION` in `sw.js` (e.g. `moving-on-v2`) whenever you edit files so installed copies refresh.

### Good to know
- The unlock code is a light gate: it is visible in the page source of a static site.
- Progress is stored in each user's own browser (localStorage); the in-app backup box transfers it between phones.
