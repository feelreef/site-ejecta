---
sitetile-page: faq
title: Questions about leaving
---

## The awkward questions, answered before you need them
%% sitetile: hero eyebrow="Questions" %%
Only about leaving and portability — this site sells nothing. Where an answer is uncomfortable, the uncomfortable answer is the one printed.

## Leaving, in nine questions
%% sitetile: grid cols=2 %%
### What if feelreef disappears tomorrow?
Your pages are markdown files, and the renderer that builds them is MIT-licensed and public. A copy of your files plus `git clone` and `npm run build` is a working site with us gone — you can run exactly that today against [this site's repo](https://github.com/feelreef/site-ejecta). The catch is the copy: your own repo lives in our GitHub organisation, so take the files out *before* you need them. [The manual](/leaving-reef) is four tool calls long.
### Do my URLs survive?
The path comes from the file name: `about.md` is `/about`. The same files rebuilt anywhere serve the same addresses. Rules for pages you retired are appended to `assets/_redirects`, a plain text file in your repo that Cloudflare Pages and Netlify both read as-is.
### Does my theme come with me?
Yes. Your look is tokens in `ir/_theme.md`, compiled to a `theme.css` that lives in your repo — and the renderer deliberately ships no named theme of its own; its `src/themes/` is empty in the public tree. Put your `theme.css` there at build time and the site looks like itself.
### Can I come back?
Yes, and leaving burns nothing: the files you took are the files we read, so coming back is the same operation in reverse. Whether that costs anything is a question for [feelreef.com](https://feelreef.com) — this site does not sell.
### Do I have to ask permission, or give a reason?
No. Every step in the manual is one you run yourself, and none of them is gated on a support ticket. The single exception is a domain *registration* transfer, and that is a registrar operation rather than an approval.
### What happens to my images?
They sit in your repo's `assets/`, served from your site root, so nothing is locked away. What is missing is the convenience: a single archive packaging content, theme and every original image is on the roadmap and not built. Today you collect them from your own site.
### What about members-only posts, orders, form submissions?
The post body is a markdown file in your repo and stays yours — the paywall is what disappears when the site leaves. A storefront's orders and payments belong to the services that ran them, and form submissions stay with the service that collected them. Content leaves; running machinery does not.
### Is there a single download-everything button?
There is an **Export my site** button on your feelreef account page, and it downloads a real file: profile, identities, purchases, and the content of the sites your account owns. For a repo-backed site like this one it does not yet contain your markdown — that comes out through the tools in the manual. Printing that here is the point of this site.
### Who owns the git repo?
We do, today: it is private, inside feelreef's GitHub organisation, and even handing the site to another person does not move the remote. You own the contents and can take them any day. **This site is the one exception** — [feelreef/site-ejecta](https://github.com/feelreef/site-ejecta) was opened on purpose so the rebuild recipe has something real to clone. That is a decision about this one site and it does not make yours public. A self-serve clone for every site is not shipped, and we are not going to call that a feature.

## The long version
%% sitetile: cta button="Read the manual"→/leaving-reef %%
Every step with the real file and tool names. [The demo](/demo) rebuilds this site from its own markdown, and [every coral](/corals) shows the format's whole vocabulary.
