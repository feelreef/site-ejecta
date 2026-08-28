---
sitetile-page: corals
title: Every coral, rendered
---
## Every coral, rendered
%% sitetile: hero eyebrow="Corals" %%
A page on this site is a stack of sections, and each section names the shape it wants — a coral. Here is every one of them, used once on real content, with the markdown that produced it printed directly underneath.

## hero, written out
%% sitetile: prose %%
You write this — you get the banner above.

```markdown
## Every coral, rendered
%% sitetile: hero eyebrow="Corals" %%
A page on this site is a stack of sections, and each section names the shape it wants — a coral. Here is every one of them, used once on real content, with the markdown that produced it printed directly underneath.
```

`hero` is the banner at the top of a page. Every section is the same three parts: a `##` heading, one `%%` line naming the coral, then ordinary markdown underneath.

## Prose is the plain one
%% sitetile: prose %%
`prose` is a block of body text, and it is what you get when you name nothing else. Headings, links, lists, tables and fenced code behave the way they do in any markdown file. Every explanation on this page — including this one — is a `prose`.

## prose, written out
%% sitetile: prose %%
You write this:

```markdown
## Prose is the plain one
%% sitetile: prose %%
`prose` is a block of body text, and it is what you get when you name nothing else. Headings, links, lists, tables and fenced code behave the way they do in any markdown file. Every explanation on this page — including this one — is a `prose`.
```

Every section starts with a `##` heading, and the `%%` line must be the very next line after it. A `%%` line that hugs nothing is not a type line at all — it is ordinary text, and it prints on the page exactly as you typed it, sentinel and all. Leave the `%%` line out and the section is still a `prose`, because prose is what a section is when it names nothing.

## Three things that leave with you
%% sitetile: grid cols=3 %%
### Your pages
Markdown files under `ir/`. The file name is the URL: `home.md` is `/`, `demo.md` is `/demo`.
### Your look
Tokens in `ir/_theme.md`, compiled into a `theme.css` that sits in the same repo.
### Your files
Anything you upload lives in `assets/` and is served from the site's root.

## grid, written out
%% sitetile: prose %%
You write this:

```markdown
## Three things that leave with you
%% sitetile: grid cols=3 %%
### Your pages
Markdown files under `ir/`. The file name is the URL: `home.md` is `/`, `demo.md` is `/demo`.
### Your look
Tokens in `ir/_theme.md`, compiled into a `theme.css` that sits in the same repo.
### Your files
Anything you upload lives in `assets/` and is served from the site's root.
```

`grid` turns every `###` into a card, and `cols=` says how many sit on a row before it wraps.

## What the folder actually holds
%% sitetile: gallery cols=3 %%
### ir/
Seven markdown files: five pages and the two config files, `_site.md` and `_theme.md`.
### theme.css
One block of CSS custom properties, compiled from the tokens in `_theme.md`.
### assets/
Uploads, served from the site root — including the wordmark in this site's header and the square mark in its browser tab.

## gallery, written out
%% sitetile: prose %%
You write this:

```markdown
## What the folder actually holds
%% sitetile: gallery cols=3 %%
### ir/
Seven markdown files: five pages and the two config files, `_site.md` and `_theme.md`.
### theme.css
One block of CSS custom properties, compiled from the tokens in `_theme.md`.
### assets/
Uploads, served from the site root — including the wordmark in this site's header and the square mark in its browser tab.
```

`gallery` is `grid`'s image-first cousin: give a card a leading image and it floats up into a figure above the text. These three carry no image, which is what a `gallery` card looks like without one.

## The manual, in order
%% sitetile: carousel cols=3 %%
### ① See what is there
`list_pages` returns every page and post, plus the two config files most people forget.
### ② Take the pages
`get_pages` reads up to a hundred files at once and hands back the markdown itself.
### ③ Take your look
`ir/_theme.md` is the source of your theme; `theme.css` is the compiled version.
### ④ Take the pictures
Everything in `assets/` is already public at your own site's root.
### ⑤ Take the history
Every edit is a commit, and each carries the sentence that asked for it.
### ⑥ Build it elsewhere
`npm run build` against the public renderer, on your machine, with no account.

## carousel, written out
%% sitetile: prose %%
You write this:

```markdown
## The manual, in order
%% sitetile: carousel cols=3 %%
### ① See what is there
`list_pages` returns every page and post, plus the two config files most people forget.
### ② Take the pages
`get_pages` reads up to a hundred files at once and hands back the markdown itself.
```

`carousel` lays the same kind of cards out as a row you scroll sideways, with arrows at the ends. `cols=` is how many are visible at once. Six cards are quoted short here; the manual has all eight steps in full.

## The tools, grouped
%% sitetile: collection link=Read the manual→/leaving-reef %%
### Reading
#### list_pages
Every page, post and config file in the site.
#### get_pages
Up to a hundred files in one call: path, markdown, version.
#### list_history
The commit log, newest first, each entry with the sentence that asked for the edit.
### Writing
#### save_page
Writes one page's whole markdown and commits it.
#### save_pages
Writes many pages as a single commit, all or nothing.
#### upload_asset
Puts a file into `assets/`, in the site's own repo.
### Shipping
#### build_preview
Builds the site and deploys it to a preview URL.
#### verify_site
Checks that every file still parses and carries the frontmatter its schema needs.

## collection, written out
%% sitetile: prose %%
You write this:

```markdown
## The tools, grouped
%% sitetile: collection link=Read the manual→/leaving-reef %%
### Reading
#### list_pages
Every page, post and config file in the site.
#### get_pages
Up to a hundred files in one call: path, markdown, version.
```

`collection` reads `###` as a group and `####` as an item inside it, and puts a jump-pill at the top for each group. `link=` adds one destination at the end.

## The life of one edit
%% sitetile: timeline style=zigzag %%
### 01 · Asked
Someone says what they want changed, in their own words. That sentence is kept.
### 02 · Written
The page's markdown is rewritten in full and validated before anything is stored.
### 03 · Committed
The write lands as a git commit in the site's own repo, carrying the sentence from step 01.
### 04 · Built
The renderer turns `ir/*.md` and `theme.css` into static HTML and CSS.
### 05 · Deployed
The built folder goes to a preview URL. Going live is a separate, human step.

## timeline, written out
%% sitetile: prose %%
You write this:

```markdown
## The life of one edit
%% sitetile: timeline style=zigzag %%
### 01 · Asked
Someone says what they want changed, in their own words. That sentence is kept.
### 02 · Written
The page's markdown is rewritten in full and validated before anything is stored.
```

`timeline` sets each `###` as one row on a spine. `style=zigzag` alternates the rows left and right.

## Where the code lives
%% sitetile: social %%
Both halves of this page are on GitHub: the site it was written from, and the renderer that built it.

- [This site's repo](https://github.com/feelreef/site-ejecta)
- [The renderer](https://github.com/CVERInc/tile)

## social, written out
%% sitetile: prose %%
You write this:

```markdown
## Where the code lives
%% sitetile: social %%
Both halves of this page are on GitHub: the site it was written from, and the renderer that built it.

- [This site's repo](https://github.com/feelreef/site-ejecta)
- [The renderer](https://github.com/CVERInc/tile)
```

`social` is the "find us elsewhere" band: a caption and a row of link buttons.

## Everything on this site
%% sitetile: tagcloud %%
- [Home](/)
- [How to leave](/leaving-reef)
- [Demo](/demo)
- [Corals](/corals)
- [Questions](/faq)

## tagcloud, written out
%% sitetile: prose %%
You write this:

```markdown
## Everything on this site
%% sitetile: tagcloud %%
- [Home](/)
- [How to leave](/leaving-reef)
- [Demo](/demo)
- [Corals](/corals)
- [Questions](/faq)
```

`tagcloud` takes a plain markdown list of links and sets it as a weighted cloud.

## Who has to exist for this page to exist
%% sitetile: people cols=2 shape=logo %%
### feelreef [the editor · the host]
The service these pages were written and built through. It runs the preview and the publish; neither is part of what you take away.
links: feelreef.com=https://feelreef.com
### CVERInc [the renderer's home]
The GitHub organisation that publishes `packages/sitetile`, the MIT-licensed renderer that turns this folder of markdown into static HTML.
links: CVERInc/tile=https://github.com/CVERInc/tile

## people, written out
%% sitetile: prose %%
You write this:

```markdown
## Who has to exist for this page to exist
%% sitetile: people cols=2 shape=logo %%
### feelreef [the editor · the host]
The service these pages were written and built through. It runs the preview and the publish; neither is part of what you take away.
links: feelreef.com=https://feelreef.com
```

`people` is a roster — of people, or of the organisations they stand for. Roles go in brackets after the name, `shape=logo` squares off the portrait, and a `links:` line adds a row of named destinations.

## A form, with nowhere to send it
%% sitetile: form submit="Send" %%
This is the markup only. A working form needs an `action` — a URL belonging to a service that receives the submission — and this site has none, because nothing here collects anything. Pressing the button reloads this page.

- Your name
- Your email
- What you are trying to take with you

## form, written out
%% sitetile: prose %%
You write this:

```markdown
## A form, with nowhere to send it
%% sitetile: form submit="Send" %%
This is the markup only. A working form needs an `action` — a URL belonging to a service that receives the submission — and this site has none, because nothing here collects anything. Pressing the button reloads this page.

- Your name
- Your email
- What you are trying to take with you
```

`form` sets a list of labels as fields and `submit=` names the button. It is also the clearest example of what step ⑥ of [the manual](/leaving-reef) means by "anything a server was doing stays behind": the shape travels, the destination does not.

## Read the manual
%% sitetile: cta button="How to leave"→/leaving-reef %%
Every step, with the real file and tool names. [The demo](/demo) rebuilds this site from its own markdown.

## cta, written out
%% sitetile: prose %%
You write this:

```markdown
## Read the manual
%% sitetile: cta button="How to leave"→/leaving-reef %%
Every step, with the real file and tool names. [The demo](/demo) rebuilds this site from its own markdown.
```

`cta` is a band with one clear action: a heading, the buttons, then whatever body text is left over as the caption underneath.

## The one that is missing
%% sitetile: prose %%
One coral is left off this wall on purpose: `faq`, the Q&A accordion. On this theme its panels do not take the same card inset as everything above, so the questions on this site are set as a plain `grid` instead — you can see them on [Questions](/faq). The other omission is `embed`, which emits raw HTML verbatim; it is the escape hatch for layouts no coral can express, and using it costs you the portability that the rest of this page is about.

And three of the corals above arrive on this page **unpainted**. `gallery`, `tagcloud` and `collection` produce the right markup — it is in the HTML, and it round-trips — but neither the renderer's base stylesheet nor this site's compiled `theme.css` carries a single rule for `.st-gallery`, `.st-tag-flow` or `.st-collection-pills`, so they land as plain text where their neighbours land as cards and pills. Nothing failed to build; the page is simply ahead of the stylesheet. That is the ordinary gap between a renderer that adds an element and a theme that has not styled it yet, and a page claiming to show you every coral is the one place it would be dishonest to hide it. Painting them here would take an `embed` block of hand-written CSS — the one move this site spends its whole length telling you not to make.
