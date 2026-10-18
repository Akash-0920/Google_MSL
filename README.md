# MSL Field Tracker

Single-file web app (`index.html`) to track doctor visits, quarterly coverage (target 2 visits/quarter), post-meeting notes (with voice input) and CSV exports.

- All data stays in the user's own browser (localStorage). Nothing is sent to any server.
- Do not enter patient data. Check company policy before storing HCP details.
- Export a JSON backup monthly (Export tab); clearing browser data erases the app data.

## Host free on GitHub Pages
1. Create a new repository and upload `index.html` and `README.md`.
2. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `(root)` → Save.
3. Open `https://<your-username>.github.io/<repo-name>/` (takes ~1 minute). Use "Add to Home Screen" on your phone.

## Multi-device sync
Export tab → Cloud sync: create a GitHub classic token with only the `gist` scope, paste it on each device. Data is stored in a secret gist (`msl-tracker-data`) in your account and syncs on open and after each change.

### Google Sheet sync (alternative)
1. New Google Sheet → Extensions → Apps Script → paste `Code.gs`, set `KEY`.
2. Deploy → New deployment → Web app → Execute as: Me → Access: Anyone.
3. Paste the Web app URL + KEY in the app (Export → Cloud sync → Option A) on each device.
The sheet gets readable tabs: Doctors, Visits, Coverage (edit in the app, not the sheet).
