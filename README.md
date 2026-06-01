<div align="center">

# Application Tracker

**A clean, fast, open-source tracker for PhD and job applications.**

No accounts. No backend. No tracking. Your data lives only in your browser.

[**→ Live demo**](#) · [**→ Deploy your own in 3 minutes**](#-deploy-your-own-copy) · [**→ Screenshots**](#screenshots)

</div>

---

## Why this exists

PhD application season is a few months of juggling 15+ universities, deadlines, professor emails, and follow-ups. Job searches look similar. Spreadsheets get messy fast. Notion is overkill. Most trackers are SaaS subscriptions you don't need.

Pipeline is a single HTML file that runs in your browser. It saves to `localStorage`, so your data never leaves your machine. Fork it, deploy it free on GitHub Pages, and you're done.

## Features

- 📋 **Two trackers in one** — PhD applications and job applications, with status workflows tailored to each
- ⏰ **Deadline countdowns** — "12d left" badges with colour-coded urgency
- 🏷️ **Status tracking** — Researching → Emailed Prof → Applied → Interview → Offer/Reject
- 🎯 **Priority &amp; fit scores** — focus on the high-value targets
- 📝 **Activity log per entry** — timestamped notes for follow-ups, replies, interviews
- 📋 **Quick Paste** — paste any text (lab page, job listing) and emails, URLs, dates, professor names get auto-extracted via regex. No API, no cost.
- 📤 **CSV export** — clean spreadsheet output any time you need it
- 💾 **JSON backup &amp; restore** — full data portability
- 🔍 **Search, filter, sort** across every field
- 📱 **Mobile-friendly** — check deadlines on your phone
- 🌓 **Light + dark mode** — auto-follows system preference
- 🔒 **100% private** — no servers, no analytics, no accounts. localStorage only.

## Deploy your own copy

The whole thing is one HTML file. Three options:

### Option 1 · Fastest (GitHub Pages, ~3 min)

1. Click **Fork** at the top right of this repo
2. In your fork, go to **Settings → Pages**
3. Under "Source", select **Deploy from a branch → main → / (root)** → Save
4. Wait ~30 seconds. Your tracker is live at `https://YOUR-USERNAME.github.io/pipeline/`

### Option 2 · Local only

Download `index.html` and double-click it. Done. Bookmark `file:///...` in your browser.

### Option 3 · Anywhere else

Upload `index.html` to Netlify, Vercel, Cloudflare Pages, or any static host. Drag-and-drop works.

## Using Pipeline

The first time you open it, you'll see example data. Click **"Clear example data &amp; start fresh"** in the intro banner, or use the menu (top-right `⋮`) → "Clear all data."

**Adding entries:** Click **Add PhD** or **Add Job**. Each form has a "Quick Paste" box at the top — paste raw text from a lab page or job listing, and emails/URLs/deadlines/prof names get extracted automatically.

**Tracking progress:** Click any row to expand it — view full details, add timestamped log entries (interview feedback, prof replies, anything). Edit and delete with the icons on hover.

**Filtering:** Use the search bar, status filter, and priority filter. Click any column header to sort.

**Exporting:** Menu (`⋮`) → **Export CSV** for spreadsheet use, or **Download JSON backup** for a complete portable copy. **Import JSON backup** restores from a backup.

## What it's not

- **Not multi-device sync.** Your data is per-browser. Export CSV/JSON if you switch machines.
- **Not multi-user collaborative.** This is intentional — each person forks their own copy.
- **Not a CRM.** It's deliberately scoped to "track applications you've started."
- **Not magic.** Quick Paste uses pattern matching (regex), not AI. It'll catch obvious things (emails, dates, prof names) but won't read between the lines. That's a feature — no API costs, no privacy concerns.

## Tech notes

- Single HTML file. No build step. No dependencies except [Tabler Icons](https://tabler.io/icons) (loaded from CDN) and Google Fonts (Fraunces, Inter, JetBrains Mono).
- Storage: browser `localStorage`. Roughly 5MB per origin, which fits hundreds of entries comfortably.
- Browser support: any browser from the last ~5 years. Tested on Chrome, Firefox, Safari.
- Source: ~950 lines of plain HTML/CSS/JS. Open it in any editor to customise.

## Customise

Open `index.html` in a text editor. Common changes:

- **Add a status type:** Find `PHD_STATUSES` or `JOB_STATUSES` arrays near the top of the `<script>` block. Add your value. Then add a matching CSS class like `.s-YourStatus { background: ...; color: ...; }`.
- **Add a field:** Add it to the form in `buildModal()`, the detail panel in `buildDetailRow()`, and the row in `buildTable()`.
- **Re-theme:** All colours are CSS variables at the top of `<style>`. Light + dark mode tokens are paired.
- **Rename:** Change "Pipeline" in the `<title>`, `.brand-name`, and footer.

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

</div>
