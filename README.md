InsightX — Product Interview & Insights (Static Demo)

A lightweight, production-looking static frontend for capturing customer interviews and viewing aggregated insights, pain points, personas, and feature ideas.
Designed to be organization-generic and easily deployable to GitHub Pages. The app reads a small config.json to inject your organization name into the UI.

What this repo contains

index.html — Login page (reads config.json and shows branded header).

dashboard.html — Main app with two tabs:

Interviews — record (dummy), attach files, save demo interviews (saved to localStorage).

Insights — aggregated insights, pain points, features, competitor snapshot, product filter, quick stats and personas (demo data).

config.json — Simple configuration JSON. Example:

{ "org": "YourOrgName" }


README.md — (this file).

Key features

Organization-branded title/header (from config.json) — ${org} InsightX.

Sticky header and tab bar.

Two top-level tabs: Interviews & Insights.

Insights tab:

Smart product filter (All, Domains, Website Builder, Email) — filters insights & pain points by product tag.

Demo lists: Insights, Pain Points, Feature Ideas, Competitive Snapshot.

Quick Stats & Top Personas (shown in the right column).

No backend required — demo data lives in the app and in localStorage.

Clean, professional UI with responsive layout and accessible markup.

Quick start
1) Add config.json

Edit config.json at repo root. Example:

{ "org": "GoDaddy" }


The app will display ${org} InsightX in the header.

2) Serve locally (recommended)

Serving from a web server avoids fetch('config.json') failing due to file:// restrictions.

Option A — Python:

# Python 3
python -m http.server 8000
# then open http://localhost:8000/index.html


Option B — Node (npx):

npx serve .
# then open the printed URL (e.g. http://localhost:3000)

3) Deploy to GitHub Pages

Create a GitHub repo (or use an existing one).

Add index.html, dashboard.html, and config.json to the repository root, commit and push to main.

In your repository → Settings → Pages → Source → choose branch main and folder / (root) → Save.

Open the published URL: https://<your-username>.github.io/<repo-name>/index.html.

How to use (demo)

Any login on index.html will open the dashboard (no authentication).

In Interviews tab: enter a title, pick a product, paste notes, click Save (demo) — saved items go to localStorage.

Switch to Insights tab to view aggregated demo insights, filter by product, view quick stats and personas.

Buttons such as Export, Contribute, and Suggest are demo placeholders and show alerts in the static demo.

Customize

Change organization name: Edit config.json (org key).

Change UI colors / fonts: Modify CSS variables at the top of each HTML file (--brand-green, --accent, etc.).

Add/remove products or demo data: Edit the DEMO_ITEMS, DEMO_FEATURES, DEMO_COMPETITORS, and DEMO_PERSONAS arrays inside dashboard.html.

Notes & limitations

This is a static demo. There is no backend — all saving is local (browser localStorage) and demo data is embedded in the page.

When opening index.html directly by double-clicking (file://), fetch('config.json') can fail. Use a local server or GitHub Pages.

Designed as a starting point — intended to be extended with real APIs, authentication, persistent storage, and real AI/analysis pipelines.
