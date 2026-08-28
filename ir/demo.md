---
sitetile-page: demo
title: Demo — this page is its own proof
---

## This page is its own proof
%% sitetile: hero eyebrow="Demo" %%
Portability is easy to claim and cheap to test. This site is five markdown files and two config files, built into static HTML by a renderer anyone can download, read and run. Here is the claim — and here is how you check it without taking our word for any of it.

## What built this page
%% sitetile: prose %%
The renderer is `packages/sitetile` in the public MIT
repo [CVERInc/tile](https://github.com/CVERInc/tile).
feelreef builds this site with that renderer; on 28
August 2026 the file that parses these pages,
`site-core.js`, was byte-identical to the public copy.

## The markdown of the section above
%% sitetile: prose %%
Not a paraphrase. This is the section you just read, exactly as it is stored in `ir/demo.md` — line breaks and all:

```markdown
## What built this page
%% sitetile: prose %%
The renderer is `packages/sitetile` in the public MIT
repo [CVERInc/tile](https://github.com/CVERInc/tile).
feelreef builds this site with that renderer; on 28
August 2026 the file that parses these pages,
`site-core.js`, was byte-identical to the public copy.
```

A `##` heading opens a section, the `%%` line names its layout, and everything under it is ordinary markdown. That is the whole grammar. There is no second, hidden format underneath, and nothing on this page came out of a database. [Every coral](/corals) does this for all twelve layouts at once.

## What you can check yourself
%% sitetile: prose %%
- **View source.** The HTML arrives finished. There is no framework runtime — what JavaScript there is amounts to a few small inline scripts (a hero effect, a keyboard handler, a header state) that make no network requests at all, so nothing on this page asks feelreef whether you are allowed to read it.
- **Read the format.** The renderer's [own README](https://github.com/CVERInc/tile/blob/main/packages/sitetile/README.md) specifies the file syntax above and marks it LOCKED — it is a published contract, not an internal detail.
- **Clone the site.** [github.com/feelreef/site-ejecta](https://github.com/feelreef/site-ejecta) is the folder these pages are built from, public and complete: `ir/`, `theme.css`, `assets/`.
- **Run it.** The commands below rebuild *this* site on your machine, offline, with no account anywhere.

## Rebuild this site yourself
%% sitetile: prose %%
Not a page *like* this one — this one, from the same seven files feelreef builds from:

```sh
git clone https://github.com/feelreef/site-ejecta
git clone https://github.com/CVERInc/tile
SITE=$PWD/site-ejecta

cd tile/packages/sitetile/astro
rm -rf content/* blog/*                  # the renderer's own demo pages

cp "$SITE"/ir/*.md     content/
cp "$SITE"/theme.css   src/themes/ejecta.css
cp -R "$SITE"/assets/. public/

npm install                              # Node 22.12 or newer
SITE_URL=https://ejecta.feelreef.com npm run build
```

`dist/index.html` is the page you are reading. The build never phones home, and the output does not need us to keep working. [The manual](/leaving-reef), step ⑥, explains what each of the three copy lines is for and how to point them at your own site.

## What this demo does not prove
%% sitetile: prose %%
Honesty is the point of the site, so here is where the demonstration stops.

**This site is not the average case.** Its repo was made public deliberately, so that the recipe above has a real thing to clone. Every other feelreef site's repo is private, and its owner gets the same folder out through the tools in the manual instead. What the clone proves is the format and the build — not that your own repo is one command away.

**“The same renderer” is a claim about code, not about bytes.** feelreef builds from its own checkout. The byte-identical check above is one file, on one date, stated so you can repeat it rather than trust it.

**The history is not in the clone.** Every edit to this site was a git commit carrying the sentence that asked for it, and that log was squashed to a single root commit when the repo went public. Step ⑤ of the manual says why, and why you should copy yours out before you need it.

## The manual
%% sitetile: cta button="How to leave"→/leaving-reef %%
Every step, with the real file and tool names. [The questions](/faq) cover what people ask on the way out.
