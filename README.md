# Internship Hub — Summer 2027

A static, mobile-friendly internship finder launchpad and application tracker for a Chemical Engineering / Materials Science student seeking Summer 2027 internships in Malaysia, Singapore, Taiwan, and China.

## What's included
- Overview of application pipeline and upcoming deadlines
- Search launchpad that **opens fresh external searches**, not an integrated job feed
- Watchlist of suggested employers (not asserted as having vacancies)
- Add, edit, search, filter, delete applications, with deadlines, notes, dates, and listing links
- Browser localStorage persistence, CSV export, JSON backup/import
- No install, build tools, API keys, or backend needed

## Run locally
Open `index.html` in a browser. For testing on localhost, run `python -m http.server 8000` in this folder and open http://localhost:8000.

## Publish on GitHub Pages
1. Make a new GitHub repository (e.g., `internship-hub`).
2. Add `index.html`, `styles.css`, and `app.js` to the repository root (and optionally this README).
3. Commit and push to the `main` branch.
4. Under **Settings → Pages**, select **Deploy from a branch**, `main`, `/(root)`, then **Save**.
5. Open the Pages URL shown by GitHub (typically `https://USERNAME.github.io/internship-hub/`).

All paths are relative and work under a GitHub Pages repository URL.

## Important limitations
- **No live jobs inside the site:** search buttons link to external platforms. There is no feed aggregation, search API, AI ranking, or automated job import yet. Job searches sometimes produce irrelevant or outdated listings; verify postings on employers' sites.
- **No cloud synchronization:** application data are stored in localStorage in *the current browser on the current device*. A different browser/device sees an empty tracker. Use JSON export/import to move or back up records. GitHub stores the website **code**, not your private application entries.
- **No background alerts:** the site flags deadlines visually when opened, but cannot notify you when closed. For notifications, add a backend, scheduled job, and notification provider.
- **No automatic status detection:** update the statuses yourself. Email integration would require OAuth authorization and a secure backend.
- **Privacy:** do not commit your JSON backups containing personal notes to a public repository. The site does not send saved applications to any server.

## Next step for automated discovery
Use a database (Supabase/Postgres), a server-side search integration with licensed job APIs or employer ATS APIs (e.g. Greenhouse/Lever where permitted), and GitHub Actions scheduled to poll at a reasonable rate. Deduplicate by ATS posting ID/URL, match the relevant date range and eligibility, then display results with timestamps and original source URLs. Do **not** put private API tokens in browser JavaScript or scrape sites against their terms.
