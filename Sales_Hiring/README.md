# Neeti SIS — Hiring Site

Static two-page hiring site for the **B2B SaaS Closer (Real Estate)** role at Neeti SIS, Kothrud, Pune.
Neeti SIS is the primary brand; Estate Autopilots appears only as operating-market credibility.

## Files

| File            | Purpose                                                        |
| --------------- | ------------------------------------------------------------- |
| `index.html`    | Page 1 — full role page (hero → credibility → product → market → role → NOT/IS → who → experience → compensation → why-now → office → **application form** → process → closing → footer) |
| `challenge.html`| Page 2 — the Sales Challenge (respond to 3 objections via WhatsApp voice notes) |
| `netlify.toml`  | Netlify config (publish dir, redirects, headers)              |
| `_redirects`    | Clean-URL rule (`/challenge` → `/challenge.html`)             |

No build step — pure HTML/CSS. Fonts: **Manrope** (headings) + **Inter** (body), loaded from Google Fonts.

## The application form (Netlify Forms)

The application on Page 1 is a **native Netlify form** (`name="closer-application"`, `data-netlify="true"`).
When a candidate submits, Netlify captures the data automatically and then redirects them to `challenge.html`
(the Sales Challenge). No server or backend needed.

- **Where submissions go:** Netlify dashboard → your site → **Forms** → `closer-application`.
- **Get notified:** in Netlify → Forms → Form notifications, add an email (or Slack/webhook) so each application pings you.
- Spam is filtered via a honeypot field (`bot-field`); you can also enable Netlify's reCAPTCHA there.
- Form detection works on drag-and-drop and Git deploys automatically because the HTML carries the Netlify attributes.

## Deploy to Netlify

**Option A — Drag & drop (fastest)**
1. Go to <https://app.netlify.com/drop>
2. Drag this whole folder onto the page.
3. Done — Netlify gives you a live URL, and Forms starts capturing applications.

**Option B — Netlify CLI**
```bash
npm install -g netlify-cli
netlify deploy --dir "." --prod
```

**Option C — Git**
Push this folder to a GitHub repo and "Import from Git" in Netlify. No build command needed; publish directory is `.` (root).

## Things to update before going live

- **WhatsApp number** — set in `challenge.html` (`phone = "918830065130"`) and linked in the `index.html` footer.
- **Metrics** — `15+`, `459+`, `14K+` live in the credibility section of `index.html`.
- **Office address** — in the office section of `index.html`.
- **Compensation** — `₹25,000` monthly floor, `2 Months` probation, `Uncapped` earnings live in the compensation section. By design the page never says "₹25K + commission"; the detailed performance-linked structure is intentionally kept off the page and explained during the interview.
- **Form notifications** — turn these on in Netlify so applications reach you (see above).
