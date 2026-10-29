# Audit Access Trackers (landing page)

A landing page for all user access trackers. Pick a **year**, then an **audit** (PwC, BDO, ...), and it opens that tracker.

This is a **separate project** from the trackers themselves. Never copy these files into a tracker repo (such as `Movex-User-Access-Tracker-2026`), because the file names overlap and would overwrite that tracker.

- Landing page: https://audit-access-trackers.delta-it-tools.workers.dev
- 2026 PwC Movex tracker: https://movex-users.delta-it-tools.workers.dev

## Files

| File | What it is |
|---|---|
| `public/index.html` | The landing page |
| `wrangler.toml` | Cloudflare settings. `name` must stay `audit-access-trackers` to match the Worker in Cloudflare |
| `package.json` | Tells Cloudflare which Wrangler version to use when deploying |

## Adding a tracker (all in the browser)

1. In this repo, open `public/index.html` and click the pencil icon to edit.
2. Find `const TRACKERS = [` near the bottom and add or change entries:

```js
{
  year: 2027,
  audits: [
    { name: "PwC", tracker: "Movex", url: "https://..." },
    { name: "BDO", tracker: "Movex", url: null }   // null shows "not set up yet"
  ]
},
```

3. Click **Commit changes**. Cloudflare redeploys automatically within a couple of minutes.

New years appear automatically, newest first. Each year can be linked directly, for example `.../#y2026`.
