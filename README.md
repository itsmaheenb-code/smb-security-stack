# The Indie Author Stack

An affiliate content site reviewing/comparing software and services for
self-published authors (editing, formatting, keyword research, distribution,
ads). Plain HTML/CSS, no build step, no dependencies — deploys on any free
static host with zero configuration.

Working name — rename freely (site title appears in every `.html` file's
`<title>`, `<header>`, and footer; find/replace "The Indie Author Stack" and
`indieauthorstack.example` once you've picked something final and checked the
domain is available).

## Preview it locally

No server needed — just open `index.html` directly in a browser, or run a
throwaway local server from this folder:

```bash
npx serve .
```

(If `npx` isn't available, opening the HTML files directly works fine too —
there's no build step to run.)

## Deploy it for free (~10 minutes, no domain needed to start)

1. Create a free [GitHub](https://github.com/signup) account if you don't have one.
2. Create a new empty repo, then from this folder:
   ```bash
   git init
   git add -A
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/indie-author-stack.git
   git push -u origin main
   ```
3. Sign up for [Cloudflare Pages](https://pages.cloudflare.com/) (free) or
   [Vercel](https://vercel.com/) (free) and connect your GitHub repo.
   - Build command: none / leave blank
   - Output directory: `/` (root)
4. You'll get a free `*.pages.dev` or `*.vercel.app` URL immediately. A real
   domain (~$10-12/year) is an easy upgrade later once the site has some
   content and traffic — not required to launch.

## Swapping in real affiliate links

Every link that should eventually be an affiliate link is marked with an
HTML comment right before it, like:

```html
<a class="cta" href="https://www.atticus.io/" rel="nofollow sponsored"><!-- AFF:atticus -->Check current Atticus pricing</a>
```

Right now these point at each tool's real (non-affiliate) homepage, so the
site is fully functional and useful before you've been approved for any
affiliate program. To activate monetization:

1. Sign up for the relevant affiliate program yourself (I can't create
   accounts on your behalf — this needs your name/tax info):
   - [Amazon Associates](https://affiliate-program.amazon.com/) — broad catalog, low commission (1-10%), useful as a fallback/general link
   - [Publisher Rocket affiliate program](https://publisherrocket.com/affiliate-program/) — ~$60/sale, 90-day cookie
   - [ProWritingAid affiliates](https://prowritingaid.com/affiliates) — ~$20/sale + $0.25/signup, 30-day cookie
   - [Grammarly affiliates](https://www.grammarly.com/affiliates) — ~$20/premium upgrade + $0.20/signup, 90-day cookie
   - Atticus, Vellum, Reedsy, Draft2Digital, AutoCrit — check each site's footer for an affiliate/partner program link; terms above were current as of research but verify before relying on them
2. Once approved, replace the `href` on each marked link with your unique
   affiliate URL, and remove the `<!-- AFF:... -->` comment.
3. Keep the `rel="nofollow sponsored"` attribute — required by Google's
   guidelines for paid/affiliate links.

## Adding new content

Follow `CONTENT-PLAYBOOK.md` — it has the exact process, style rules, and a
topic backlog so new posts stay consistent with the first three.

## Automating ongoing content

Once this is pushed to GitHub with hosting connected (auto-deploys on push),
you can ask Claude Code to set up a recurring scheduled task that:

1. Picks the next topic from `CONTENT-PLAYBOOK.md`'s backlog
2. Researches it and writes a new post following the playbook
3. Wires it into `index.html` and `sitemap.xml`
4. Commits and pushes — which auto-deploys

That's a good next step once the first few posts are live and you've
confirmed the deploy pipeline works end to end.

## Legal basics already handled

- `disclosure.html` — FTC-required affiliate disclosure, linked in every
  page footer and at the top of every post with affiliate links.
- Every post with affiliate links carries a disclosure note near the top,
  not just in the footer — required for FTC compliance, not just nice-to-have.

Still worth doing before real traffic: replace the placeholder contact email
in `disclosure.html`, and double check your specific affiliate programs'
disclosure requirements (some, like Amazon Associates, have their own
required wording in addition to the FTC disclosure).
