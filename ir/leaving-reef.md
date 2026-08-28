---
sitetile-page: leaving-reef
title: How to leave feelreef with your whole site
---

## How to leave, step by step
%% sitetile: hero eyebrow="The manual" %%
No permission, no exit interview, no ticket to file. What it does take is about twenty minutes, a text editor, and — for the last step — Node on your machine. Read it before you need it, not on the day.

## Before you start
%% sitetile: prose %%
There are two doors out, and they are not equally good today.

The one that works for a repo-backed site like this one is **the tools**: an AI assistant connected to feelreef over MCP — the same connection these pages were written through. Every tool named below is one you can ask for by name.

The other is the **Export my site** button on your account page at feelreef.com. It downloads a real file rather than a promise, but read step ⑦ before you rely on it, because what it contains today is not your markdown.

## ① See what is actually there
%% sitetile: prose %%
`list_pages` returns every page and post — plus the two config files most people forget:

```
list_pages  site: "yoursite"
→ pages:      ir/home.md · ir/leaving-reef.md
             ir/demo.md · ir/corals.md · ir/faq.md
  siteConfig: ir/_site.md · ir/_theme.md
```

The `siteConfig` files are not routable pages, which is why they are listed separately — and they carry your nav, footer, brand, fonts and theme. Take them.

## ② Take the pages
%% sitetile: prose %%
`get_pages` reads up to a hundred files in one call and hands back each one's path and markdown:

```
get_pages  site: "yoursite"
           paths: ["ir/home.md", "ir/_theme.md"]
→ [{ path, markdown, version }, …]
```

Save each `markdown` to a file of the same name. That is the export: there is no conversion, because what you are copying is already the source. `get_page` does one file at a time and parses it as well, if you would rather read it than store it.

## ③ Take your look
%% sitetile: prose %%
`ir/_theme.md` is your theme's source — a list of tokens. The renderer eats a compiled `theme.css`, which also lives in your repo and is a mechanical translation of exactly those tokens:

```css
/* Compiled from ir/_theme.md — do not hand-edit. Theme: ejecta. */
html:root {
  --gd-bg: #f1f2f4;
  --gd-accent: #c6472a;
}
html[data-theme="dark"]:root {
  --gd-bg: #14161b;
}
```

If you have that file, keep it. If you only have `_theme.md`, you can write the block by hand in a few minutes: every `gd-*` line becomes one `--gd-*` declaration, and every `gd-*@dark` line goes in the dark block. Nothing about your look hides in the renderer — its `src/themes/` directory ships empty precisely so that a site's design belongs to the site.

## ④ Take the pictures
%% sitetile: prose %%
Images you uploaded live in the repo's `assets/` and are served from your site's root, so `assets/logo.svg` is `https://yoursite/logo.svg`. The reliable way to collect them today is from your own live site: the URLs are the ones already written into your pages.

**Not yet:** one call that hands you content, theme and every original image as a single archive. It is on feelreef's roadmap and it is not built. Today you assemble the folder yourself.

## ⑤ Take the history
%% sitetile: prose %%
Every edit is a git commit, and each one carries the sentence that asked for it — so the log reads as plain language rather than a list of hashes:

```
list_history  site: "yoursite"
→ [{ sha, date, author, message, prompt }, …]
```

`list_versions` shows what was published and when, `diff_versions` compares any two points, and `restore_version` / `restore_page` roll an old state forward as a new version rather than rewriting anything.

**Copy it out before you go**, because it is the one thing a folder of files does not carry on its own — and because a history is the easiest part of a site to lose. This site is its own cautionary example: when its repo was opened to the public, the history was rewritten to a single root commit, since the earlier messages were internal working notes in another language that were never written to be read. Those entries are gone and nobody kept a copy. A squash is a decision someone makes once, in a second.

## ⑥ Build it somewhere else
%% sitetile: prose %%
The renderer is public and MIT-licensed, and so is this site — which means this is not a sketch of a recipe, it is the recipe, and you can run it right now:

```sh
git clone https://github.com/feelreef/site-ejecta
git clone https://github.com/CVERInc/tile
SITE=$PWD/site-ejecta

cd tile/packages/sitetile/astro
rm -rf content/* blog/*                  # the renderer's own demo pages and posts

cp "$SITE"/ir/*.md     content/          # your pages, plus _site.md and _theme.md
cp "$SITE"/theme.css   src/themes/ejecta.css
cp -R "$SITE"/assets/. public/           # everything served from the site root

npm install                              # Node 22.12 or newer
SITE_URL=https://ejecta.feelreef.com npm run build
```

The build reads `content/*.md` — including `_site.md` and `_theme.md` — and writes static HTML and CSS into `dist/`. Three details our internal deploy wrapper handles for you, and that you are now doing by hand:

- **Pages go in `content/`**, and the renderer's own demo pages are already sitting there. Clear them first or they build alongside yours.
- **The theme goes to `src/themes/<name>.css`**, where `<name>` is the value of the `theme:` key in your `_site.md` — here, `ejecta`. Our wrapper refuses to build when that file is missing; a plain `npm run build` quietly falls back to the bare skin instead, so check it is in place before you judge the result.
- **Assets go in `public/`**, which is what makes `/wordmark.svg` in the header resolve.

To build **your** site instead of this one, point those three copy lines at your own folder. Nothing else changes.

## ⑦ The account-page button, honestly
%% sitetile: prose %%
Your feelreef account page has an **Export my site** button, and it downloads a real archive: your profile, your connected identities, your purchases, and the content of the sites your account owns.

What it is **not**, today: the markdown of a repo-backed site like this one. That export reads the older block-based content model, so a site whose pages live as markdown in a git repo comes out through steps ① to ⑤ instead. We would rather print that here than have you discover it on the day you leave.

## ⑧ Your domain, your DNS
%% sitetile: prose %%
Pointing a domain at feelreef is a DNS record you control, and un-pointing it is the same record. Change it whenever you like; nothing here holds it and nobody needs to approve it. If you *bought* the domain through feelreef, moving the registration itself is an ordinary registrar transfer — ask and we will start it. It is not a button in the console today.

## What you cannot take
%% sitetile: prose %%
A list of what leaves is only half the truth, so here is the other half:

- **The git remote, usually.** Your site's repo is private, in feelreef's GitHub organisation, and handing the site to another person does not move it. You take the contents, not the remote. This site is the one exception, made public on purpose so that step ⑥ has something real to clone — and it does not make yours public.
- **The build and the hosting.** `build_preview`, `publish_site` and the Pages projects behind them are ours. Rebuilding is step ⑥, and it is yours.
- **Anything a server was doing.** Members-only posts become ordinary public files, a storefront stops taking orders, form submissions stay with the service that collected them.
- **The one-file archive.** Not built yet, as in step ④.

## The questions people ask on the way out
%% sitetile: cta button="Read the questions"→/faq %%
The awkward ones, answered without a retention flow. [The demo](/demo) is this same claim, checked on this site.
