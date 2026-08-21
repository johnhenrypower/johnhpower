# personal-website

`johnhpower.com`. A single page: John's name, a two-paragraph intro positioning him
on agentic commerce, and two links (Substack, LinkedIn).

**Live.** GitHub Pages, from `johnhenrypower/johnhpower`, which is public.

## What's in here

The site itself, plus `CLAUDE.md` with the design direction, the URLs, and the
hosting decision.

Three subdirectories are **dead weight**: `skiing-photos/`, `spotify-dashboard/`
and `strava-dashboard/`. Those subdomains were retired 2026-08-07 — DNS removed,
repos flipped private, Pages unpublished. The local folders and their `CLAUDE.md`
files are leftovers. They are untracked by git, so deleting them is
unrecoverable, which is why they are still here pending a decision.

## The 2026-08-07 rewrite

The site used to be a card grid: Strava, Playlists, Skiing, Writing, LinkedIn,
plus a "product builder / skier / backgammon player" descriptor row. All removed.

It is now one page that says what John works on. The reason is positioning: the
site's job is to make agentic commerce legible to someone who just met him, not to
be a personal dashboard.

## Why it stays on GitHub Pages

Considered moving to Cloudflare Pages so the repo could go private, matching
`shop-johnhpower`. **Rejected**, and worth not re-proposing.

Apex custom domains on Cloudflare Pages require the zone to live on Cloudflare via
CNAME flattening. That means moving nameservers off GoDaddy and re-creating the
MX, SPF, DKIM and DMARC records carrying **`agent@johnhpower.com`** — live
infrastructure behind `agent-gmail-mcp`, `market-intelligence` and
`evening-brief`.

Not worth risking mail delivery to make a static site private when it is public by
design. Full reasoning in `CLAUDE.md`.

## Ordering rule, learned here

When retiring a subdomain: **remove the DNS record before unpublishing Pages.** The
other order leaves a dangling CNAME, which is a subdomain-takeover vector.
