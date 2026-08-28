---
sitetile-page: home
title: REEF with Ejecta, from feelreef — how to leave with your whole site
---

## Your site is yours. Here is how you take it.
%% sitetile: hero eyebrow="Ejecta" %%
This is the exit manual for a feelreef site: what leaves with you, where it lives, what stays behind, and the real command that rebuilds your site on your own machine. The page you are reading was built from its own markdown by a renderer anyone can download — and this site's own repo is public, so you can clone it and build this page yourself.

## What “eject” actually hands you
%% sitetile: prose %%
A feelreef site is a folder of plain text files. Not a database row, not a proprietary blob, not an export format invented for the occasion — these files **are** the site, and they are exactly what the renderer reads:

```
your-site/
├─ ir/
│  ├─ home.md          →  /
│  ├─ leaving-reef.md  →  /leaving-reef
│  ├─ _site.md         nav, footer, brand, fonts
│  └─ _theme.md        palette, type, shape — as tokens
├─ theme.css          your look, compiled from _theme.md
└─ assets/            images, and _redirects
```

A page is markdown plus one line per section — `%% sitetile: grid cols=3 %%` — naming its layout. `home.md` becomes `/`, `about.md` becomes `/about`. Open any of it in a text editor and it reads as text; that is the entire content model. [Every coral](/corals) shows all twelve of those layout names rendered once each, with the markdown that produced them.

## Travels with you
%% sitetile: grid cols=3 %%
### Every page, verbatim
Read back with `get_pages`, up to a hundred files in one call, and what comes back is the markdown itself — no conversion step that reinterprets anything on the way out.
### Your look
`ir/_theme.md` holds the palette, type and shape as tokens; `theme.css` is those tokens compiled into one block of CSS custom properties, and it lives in your repo. The renderer ships no named theme at all — its `src/themes/` directory is empty in the public tree, on purpose.
### Your pictures and redirects
Uploaded media lives in `assets/` and is served from your site's root. Retire a page and its forwarding rule is appended to `assets/_redirects` — a plain text file that travels with the folder and that other static hosts read as-is.

## Stays behind
%% sitetile: grid cols=3 %%
### The hosting
Preview builds, publishing, the Cloudflare Pages projects underneath: ours. Leaving means building the site yourself — one command, below — and putting the output on a host you choose.
### The git remote, usually
Every site's repo lives in feelreef's GitHub organisation and is private by default; handing the site to another person does not move the remote, and there is no self-serve clone. **This site is the deliberate exception** — its repo is public so the recipe below has something real to clone. Yours is not, unless you ask.
### Anything with a server behind it
A members-only post becomes an ordinary markdown file once the paywall stops. Orders, payments and form submissions belong to the services that ran them. Your words leave; the machinery around them does not.

## Running it somewhere else
%% sitetile: prose %%
The renderer is public and MIT-licensed: [github.com/CVERInc/tile](https://github.com/CVERInc/tile), package `packages/sitetile`. So is this site: [github.com/feelreef/site-ejecta](https://github.com/feelreef/site-ejecta). Together they are a build you can run end to end on your own machine, with no account anywhere:

```sh
git clone https://github.com/feelreef/site-ejecta
git clone https://github.com/CVERInc/tile
SITE=$PWD/site-ejecta

cd tile/packages/sitetile/astro
rm -rf content/* blog/*                  # the renderer's own demo pages

cp "$SITE"/ir/*.md     content/          # five pages + _site.md + _theme.md
cp "$SITE"/theme.css   src/themes/ejecta.css
cp -R "$SITE"/assets/. public/           # wordmark, icon, robots.txt, _redirects

npm install                              # Node 22.12 or newer
SITE_URL=https://ejecta.feelreef.com npm run build
```

`dist/` is this site: seven pages of static HTML and CSS you can drop on any host. Point the same three copy lines at your own `ir/`, `theme.css` and `assets/` and it builds your site instead. [The manual](/leaving-reef) walks every step, starting with how to get your own files out in the first place.

## Moving in is the other direction
%% sitetile: prose %%
If you came looking for the way *in* — bringing an existing Wix, WordPress or Squarespace site across to feelreef — that is sold at [feelreef.com/atoll/ejecta](https://feelreef.com/atoll/ejecta), not here.

## Read the manual
%% sitetile: cta button="How to leave"→/leaving-reef %%
Step by step, with the real file and tool names. [The demo](/demo) checks the claim on this site itself, and [every coral](/corals) shows what the format can draw.
