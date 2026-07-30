# FormDock Astro Starter

A one-page Astro site for freelancers and small studios — fast, accessible,
**zero JavaScript** — with a working contact form powered by
[FormDock](https://formdock.app): submissions get spam-filtered, stored, and
emailed to you. No backend, no serverless functions, nothing to maintain.

**Live demo:** https://starter-demo-beta.vercel.app
([demo source](https://github.com/form-dock/starter-demo) — the template with
one file edited)

**Live in 5 minutes:**

## 1. Get your form endpoint

1. Create a free account at [formdock.app](https://formdock.app)
   (100 submissions/month, no card)
2. Create a workspace, then a form inside it
3. Copy the form's endpoint URL (looks like `https://formdock.app/f/abc123…`)

## 2. Wire it up

```bash
npm install
```

Open **`src/config.ts`** and paste your endpoint (plus your site name):

```ts
export const FORMDOCK_ENDPOINT = "https://formdock.app/f/your-key-here";
export const SITE_NAME = "Your Studio";
```

```bash
npm run dev
```

Open http://localhost:4321/contact and send yourself a test message — it
appears in your FormDock dashboard and your inbox.

## 3. Deploy anywhere

> ⚠️ When importing to Vercel/Netlify, make sure you import **your copy** of
> the repo (created via "Use this template"), not this template itself — the
> template ships with the placeholder key.

It's a fully static site (`npm run build` → `dist/`), so any static host
works: Vercel, Netlify, Cloudflare Pages, GitHub Pages, an S3 bucket. No
environment variables, no server config.

**Recommended after deploying:**

- In your FormDock form settings, set the **redirect URL** to
  `https://your-site.com/thanks` so submitters land on this site's own
  thanks page
- Add your domain under **allowed domains** to lock the endpoint's CORS to
  your site

## What you get

- **Working contact form** — spam-filtered (honeypot included), stored,
  emailed; searchable archive + CSV export in the FormDock dashboard
- **One-page layout** — hero, work, services, contact — swap the copy and go
- **Dark mode** via `prefers-color-scheme`, system fonts, no CSS framework
- **Zero client JavaScript** — Astro ships plain HTML

## Customizing

Everything visual lives in three places: `src/layouts/Base.astro` (shell +
design tokens — change `--accent` to re-theme the whole site),
`src/pages/index.astro` (content), and `src/components/ContactForm.astro`
(add fields freely — any `name="…"` input shows up in your submissions and
notification emails automatically; no config needed).

## Docs

- [FormDock Astro guide](https://formdock.app/docs/astro)
- [Dashboard guide](https://formdock.app/docs/dashboard) — routing
  notifications, spam review, exports, webhooks
- [All docs](https://formdock.app/docs)

MIT licensed — use it for client work freely.
