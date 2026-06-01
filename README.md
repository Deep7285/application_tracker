<div align="center">

# Application Tracker

**A clean, fast, open-source tracker for PhD and job applications.**

No accounts. No backend. No tracking. Your data lives only in your browser.
[**→ Live demo**](https://deep7285.github.io/application_tracker/)

</div>

---
## Screenshots
<p align="center">
  <img src="https://github.com/user-attachments/assets/56ab500a-f35e-4fc8-8bd9-b985ed68a78c" width="48%" alt="image" />
  <img src="https://github.com/user-attachments/assets/612b2341-b9b4-41b0-b1ff-6ec7926fb358" width="48%" alt="image" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/a273f464-d857-4c71-993c-c7993554a030" width="48%" alt="image" />
  <img src="https://github.com/user-attachments/assets/e26662fc-d953-4204-8034-ebbd425a12c2" width="48%" alt="image" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/18865d19-79ca-4b4a-b4cf-271ffef1eb6f" width="48%" alt="image" />
  <img src="https://github.com/user-attachments/assets/5e333dea-a26b-45f1-ba72-cb831c289bd2" width="48%" alt="image" />
</p>

</div>

---


## Why this exists

Application seasons — whether for PhDs, postdocs, research roles, or industry jobs — turn into a few months of juggling many things at once: deadlines, professor emails, application portals, cover letter versions, interview rounds, recruiter follow-ups, offer responses. The information piles up fast.

The usual options don't fit well:

- **Spreadsheets** get messy after a dozen rows. Status columns become inconsistent, deadlines fall off your radar, and there's no good place to log "prof replied today, asked for research statement."
- **Notion** is powerful but heavy. You spend more time tweaking the database than tracking applications.
- **Job-tracker SaaS tools** charge a subscription and store your data on their servers.
- **Sticky notes and inbox flags** stop working past 5 applications.

Application Tracker is a single HTML file that runs in your browser. PhD applications and job applications each get their own page with workflows that actually match how those processes work — PhD tracking cares about professor contact, research fit, and lab pages; job tracking cares about application date, recruiter contact, and OA stages.

It saves to your browser's `localStorage`, so your data never leaves your machine. Fork it, deploy it free on GitHub Pages, and you're done.

## Features

- 📋 **Two trackers in one** — PhD applications and job applications, with status workflows tailored to each
- 🧭 **Opportunities directory** — a curated tab of legitimate, hand-verified sources for PhD positions, fellowships, and industry research jobs (EURAXESS, FindAPhD, DeepMind, MSR, and more)
- 🔖 **Quick Add Bookmarklet** — install a one-click bookmark; while browsing any lab page or job listing, click it to instantly open Application Tracker with the page's text pre-loaded for parsing
- ⏰ **Deadline alerts** — banner alerts surface deadlines within 7 days (urgent) and 14 days (planning ahead)
- 💾 **Smart backup reminders** — nudges you when your data hasn't been backed up in over a week
- 🔄 **Restore from JSON anywhere** — download a backup on one device, upload it on another. That's how you sync across phone/laptop without a backend.
- 🏷️ **Status tracking** — *PhD:* Researching → Emailed Prof → Applied → Interview → Offer/Reject. *Jobs:* Saved → Applied → OA → Interview → Offer/Reject.
- 🎯 **Priority &amp; research-fit scores** — focus on the high-value targets
- 📝 **Activity log per entry** — timestamped notes for follow-ups, replies, interviews
- 📋 **Quick Paste** — paste any text (lab page, job listing) and emails, URLs, dates, professor names get auto-extracted via regex. No API, no cost.
- 📤 **CSV export** — clean spreadsheet output any time you need it
- 🔍 **Search, filter, sort** across every field
- 📱 **Mobile-friendly** — check deadlines on your phone
- 🌓 **Light + dark mode** — auto-follows system preference
- 🔒 **100% private** — no servers, no analytics, no accounts. localStorage only.

## Using Application Tracker across devices

Application Tracker has **no backend** — your data lives in your browser's `localStorage`. To use it on multiple devices (laptop + phone, work + home), use the JSON backup/restore flow:

1. On your primary device: open the menu (`⋮`) → **Download JSON backup** (or click "Download backup now" in the reminder banner)
2. Save the file (e.g. `application_backup_2025-12-01.json`) somewhere accessible — Google Drive, Dropbox, iCloud, or just email it to yourself
3. On the other device: open the same URL → menu → **Restore from backup** → pick the file → click **Restore data**

That's it. No accounts, no signups. The reminder banner will nudge you to backup again after 7 days of changes, so you're unlikely to lose work.

**Tip:** Make a habit of downloading a backup before any major work — clearing browser data, switching devices, or right before deadlines. Treat it like saving a Word document.

## Using Application Tracker

The first time you open it, you'll see example data. Click **"Clear example data &amp; start fresh"** in the intro banner, or use the menu (top-right `⋮`) → "Clear all data."

**Adding entries:** Click **Add PhD** or **Add Job**. Each form has a "Quick Paste" box at the top — paste raw text from a lab page or job listing, and emails/URLs/deadlines/prof names get extracted automatically.

**Tracking progress:** Click any row to expand it — view full details, add timestamped log entries (interview feedback, prof replies, anything). Edit and delete with the icons on hover.

**Filtering:** Use the search bar, status filter, and priority filter. Click any column header to sort.

**Exporting:** Menu (`⋮`) → **Export as CSV** for spreadsheet use, or **Download JSON backup** for a complete portable copy. **Restore from backup** loads a previously downloaded JSON file.

## Deploy your own copy

The whole thing is one HTML file. Three options:

### Option 1 · Fastest (GitHub Pages, ~3 min)

1. Click **Fork** at the top right of this repo
2. In your fork, go to **Settings → Pages**
3. Under "Source", select **Deploy from a branch → main → / (root)** → Save
4. Wait ~30 seconds. Your tracker is live at `https://YOUR-USERNAME.github.io/application_tracker/`

### Option 2 · Local only

Download `index.html` and double-click it. Done. Bookmark `file:///...` in your browser.

### Option 3 · Anywhere else

Upload `index.html` to Netlify, Vercel, Cloudflare Pages, or any static host. Drag-and-drop works.

## What it's not

- **Not multi-device sync.** Your data is per-browser. Export CSV/JSON if you switch machines.
- **Not multi-user collaborative.** This is intentional — each person forks their own copy.
- **Not a CRM.** It's deliberately scoped to "track applications you've started."
- **Not magic.** Quick Paste uses pattern matching (regex), not AI. It'll catch obvious things (emails, dates, prof names) but won't read between the lines. That's a feature — no API costs, no privacy concerns.

## Tech notes

- Single HTML file. No build step. No dependencies except [Tabler Icons](https://tabler.io/icons) (loaded from CDN) and Google Fonts (Fraunces, Inter, JetBrains Mono).
- Storage: browser `localStorage`. Roughly 5MB per origin, which fits hundreds of entries comfortably.
- Browser support: any browser from the last ~5 years. Tested on Chrome, Firefox, Safari.
- Source: ~1200 lines of plain HTML/CSS/JS. Open it in any editor to customise.

## Customise

Open `index.html` in a text editor. Common changes:

- **Add a status type:** Find `PHD_STATUSES` or `JOB_STATUSES` arrays near the top of the `<script>` block. Add your value. Then add a matching CSS class like `.s-YourStatus { background: ...; color: ...; }`.
- **Add a field:** Add it to the form in `buildModal()`, the detail panel in `buildDetailRow()`, and the row in `buildTable()`.
- **Re-theme:** All colours are CSS variables at the top of `<style>`. Light + dark mode tokens are paired.
- **Change the logo:** Search for `BRAND_LOGO_SVG` in the script — it's a small inline SVG you can replace.

## License

MIT. Use it, modify it, ship it, fork it. Attribution appreciated but not required.

## Contributing

Pull requests welcome. Small, focused changes preferred. If you're considering a big feature, open an issue first.

Useful additions that fit the spirit of the project:
- More date format support in Quick Paste
- Additional status workflows (internships, fellowships)
- Keyboard shortcuts
- Print stylesheet for offline review

Out of scope:
- Backends, accounts, cloud sync (defeats the purpose)
- Heavy frameworks (it's deliberately vanilla)
- AI-powered features that need paid APIs

---

<div align="center">

Built for researchers and applicants who'd rather focus on writing the SOP than fighting their tracker.

© 2025 Deepak Kumar · MIT licensed

</div>
