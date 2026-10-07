# Luminate UTM Link Builder

A one-page tool for building consistent, trackable campaign links (UTMs) and keeping a running log of the ones you've made. Live at **https://bczarny.github.io/lum-utm/**

It's a single file — `index.html` — with no build step, no dependencies, and no server. Just host it.

---

## Update the live site (dead-easy, no coding)

The repo and GitHub Pages are already set up. You only need to replace one file.

1. Go to **https://github.com/bczarny/lum-utm**
2. Click **Add file → Upload files**
3. Drag the new **`index.html`** into the box (it replaces the old one)
4. Click **Commit changes** (green button at the bottom)
5. Wait ~1 minute, then open **https://bczarny.github.io/lum-utm/** and hard-refresh (Cmd/Ctrl+Shift+R)

That's it. The new version is live.

> Prefer the command line? From the repo folder:
> ```bash
> cp /path/to/index.html .
> git add index.html && git commit -m "Update UTM builder" && git push
> ```

---

## What it does

- **Builds the link** — enter the destination URL + `utm_source`, `utm_medium`, `utm_campaign` (and optional `content` / `term`); the full tagged URL is generated live with **Copy link** and **Copy as Markdown** buttons.
- **Keeps you consistent** — values are auto-normalized (lowercase, spaces → hyphens) so GA4 doesn't split `LinkedIn` from `linkedin`. Fields suggest Luminate's standard source / medium / campaign values.
- **Keeps a running log** — every link you generate is saved to a history table (saved in your browser). Copy or delete any row, copy all URLs, or **Export CSV** to share with the team or commit to this repo.
- **Teaches it** — a built-in "How UTMs work & Luminate conventions" cheat sheet.

## Conventions it follows

| Tag | Meaning | Examples |
|---|---|---|
| `utm_source` | the platform | `linkedin`, `instagram`, `x`, `reddit`, `bluesky`, `newsletter`, `email` |
| `utm_medium` | the channel type | `social` (organic), `paid_social` (ads), `email`, `newsletter`, `referral` |
| `utm_campaign` | the initiative | `2026-09-release-strategies`, `2026-09-hybe-case-study` (format: `yyyy-mm-topic`) |
| `utm_content` | variant / placement | `carousel`, `single-image`, `reel`, `story`, `bio-link` |
| `utm_term` | paid keyword | leave blank for organic |

**House rules:** lowercase only, hyphens not spaces, one value per concept, and only tag links that point to `luminatedata.com` (never a link from one of our pages to another). Once tagging starts, this traffic moves out of **Referral** and into **Organic Social** in the reports — that's the tagging working, not a performance change.

## A note on the history log

The running list is stored in **your browser** (localStorage), so it isn't shared across people automatically. Use **Export CSV** to pool everyone's links or commit the log to this repo. If you'd rather have a single shared log for the whole team, that needs a small backend (or a connected Google Sheet) — ask in **#luminate-marketing-analytics**.
