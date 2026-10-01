# APEX — Modular Coach × Scarci (offline-capable PWA)

Single-page training app: 20-block modular programming, three one-tap year presets (Hyrox · Climber/Runner · Recomp), live session + cardio logging, 1RM tiles with % → kg, Extras (generators, fatigued runs, Invictus-style, 21-15-9), embedded Hyrox Forge, Fuel/Work/Tendon, searchable Index. **Works fully offline once installed.**

## Deploy (GitHub Pages) — upload ALL files
1. Create a repository (e.g. `apex`)
2. **Add file → Upload files** → drag in **all of**: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png` → Commit
   (GitHub's web uploader takes multiple files at once — select them all together)
3. **Settings → Pages** → Deploy from a branch → `main` / `(root)` → Save
4. Open `https://<your-username>.github.io/apex/` once **while online**
5. Safari → Share → **Add to Home Screen**

## Offline behaviour
- The service worker (`sw.js`) caches the entire app on first visit; after that it opens and works with no connection — on the train, in theatre basements, anywhere
- All data (logs, 1RMs, plan edits) lives in on-device storage and never needed the network anyway
- Updates: overwrite the files in the repo; the app picks up the new version next time it's opened online (network-first), and keeps working offline on the old version until then
- `index.html` alone still works online if you ever deploy just that file — the other four files are what add offline + the home-screen icon

## Notes
- Data is per-device: use **Export** on the Plan tab regularly and before changing phones
