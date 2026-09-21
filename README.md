# The SMB Security Stack

**Live at: https://itsmaheenb-code.github.io/smb-security-stack/**

An affiliate content site reviewing/comparing security and backup software for
small businesses and remote teams (password managers, business VPNs, cloud
backup, and related tools). Plain HTML/CSS, no build step, no dependencies —
hosted free on GitHub Pages, auto-deploys on every push to `main`.

Working name — rename freely (site title appears in every `.html` file's
`<title>`, `<header>`, and footer; find/replace "The SMB Security Stack" and
`smbsecuritystack.example` once you've picked something final and checked the
domain is available). Note: if you rename the GitHub repo itself, the live
URL changes too, and every `<link rel="canonical">`, `sitemap.xml`, and
`robots.txt` entry needs updating to match (grep for
`itsmaheenb-code.github.io/smb-security-stack` to find them all).

## Preview it locally

No server needed — just open `index.html` directly in a browser, or run a
throwaway local server from this folder:

```bash
npx serve .
```

(If `npx` isn't available, opening the HTML files directly works fine too —
there's no build step to run.)

## Deployment (done)

Live on GitHub Pages at https://itsmaheenb-code.github.io/smb-security-stack/,
serving directly from the `main` branch, root path — no build step, no
separate hosting account. Every `git push` to `main` triggers a new Pages
build automatically (usually live within ~30-60 seconds).

To trigger a rebuild manually if needed:
```bash
gh api -X POST repos/itsmaheenb-code/smb-security-stack/pages/builds
```

A real domain (~$10-12/year) is an optional upgrade later once the site has
traffic — not required. If you add one, update the canonical/sitemap/robots.txt
URLs (see the note above) and add it under the repo's Settings → Pages →
Custom domain.

## Swapping in real affiliate links

Every link that should eventually be an affiliate link is marked with an
HTML comment right before it, like:

```html
<a class="cta" href="https://1password.com/business" rel="nofollow sponsored"><!-- AFF:1password -->Check 1Password Business pricing</a>
```

Right now these point at each tool's real (non-affiliate) homepage, so the
site is fully functional and useful before you've been approved for any
affiliate program. To activate monetization:

1. Sign up for the relevant affiliate/partner program yourself (I can't
   create accounts on your behalf — this needs your name/tax info):
   - [1Password Partners](https://1password.com/partners) — business password manager
   - [NordPass affiliate program](https://nordpass.com/affiliate-program/) — reported up to 50%+ recurring on some Nord programs; verify current terms
   - [NordLayer affiliates](https://nordlayer.com/affiliates/) — reported up to 50% commission, 30-day cookie
   - [Backblaze affiliate program](https://www.backblaze.com/) — check footer for current partner program link
   - Bitwarden, Tailscale, Check Point, iDrive, Acronis, CrashPlan — check each site's footer for an affiliate/partner program link; terms in the posts were current as of research but verify before relying on them
2. Once approved, replace the `href` on each marked link with your unique
   affiliate URL, and remove the `<!-- AFF:... -->` comment.
3. Keep the `rel="nofollow sponsored"` attribute — required by Google's
   guidelines for paid/affiliate links.

## Adding new content

Follow `CONTENT-PLAYBOOK.md` — it has the exact process, style rules, and a
topic backlog so new posts stay consistent with the first three.

## Automating ongoing content

The site is live and auto-deploys on push, so this is ready to set up: a
recurring scheduled task that picks the next topic from
`CONTENT-PLAYBOOK.md`'s backlog, researches it, writes a new post following
the playbook (including the GEO/AEO markup), wires it into `index.html` and
`sitemap.xml`, and commits + pushes — which auto-deploys live within a minute.

## Legal basics already handled

- `disclosure.html` — FTC-required affiliate disclosure, linked in every
  page footer and at the top of every post with affiliate links.
- Every post with affiliate links carries a disclosure note near the top,
  not just in the footer — required for FTC compliance, not just nice-to-have.

Still worth doing before real traffic: replace the placeholder contact email
in `disclosure.html`, and double check each affiliate program's specific
disclosure requirements in addition to the general FTC disclosure.
