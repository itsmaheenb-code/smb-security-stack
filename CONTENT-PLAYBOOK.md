# Content playbook

How new posts get added to this site — follow this exactly so every post matches
in structure, tone, and honesty about what is/isn't affiliate-linked. This is
written so either Michelle or a future Claude Code session (manual or scheduled)
can produce a consistent post from it.

## Process for one new post

1. **Pick a topic** from the backlog below (or a new one that fits the same
   pattern: "Best [category of security/backup tool] for small business / remote teams").
2. **Research current facts with web search** — pricing, per-seat cost, platform
   support, affiliate program terms (commission, cookie length). Do not reuse
   numbers from an old post without reverifying; SaaS pricing and even product
   names change often (e.g. Perimeter 81 → Check Point Harmony SASE).
3. **Write the post** using `posts/best-password-manager-for-small-business.html`
   as the template — copy its exact structure, don't improvise a new one:
   - Header includes the logo badge: `<span class="logo-badge">S</span>The SMB Security Stack`.
   - Right after `<main>`, a `<span class="post-tag tag-X">Category</span>` —
     reuse an existing tag class (`tag-password`, `tag-vpn`, `tag-backup`,
     `tag-endpoint`, `tag-mfa`) if the topic fits one, or add a new
     `.tag-newcategory` rule to `assets/style.css` (pick an unused accent
     color already defined as a CSS variable) if it doesn't.
   - Comparison table, then one `<div class="tool-card"><h2>...</h2><span
     class="price-chip">...</span><p>...</p><a class="cta" href="..."
     rel="nofollow sponsored"><!-- AFF:x -->...</a></div>` per tool. Use
     `class="cta"` only on the affiliate-pending link; use `class="plain-link"`
     for a tool with no affiliate program.
   - A closing `<div class="verdict-box"><h2>Which one should you pick?</h2>
     <p>...</p></div>` addressed to different reader situations (team size,
     budget, technical sophistication).
   - FAQ as `<details class="faq-item"><summary>Question?</summary><p
     class="faq-answer">Answer.</p></details>` — not plain `<h3>`/`<p>`, and
     not `<summary>` styling changes; the CSS already handles the accordion look.
   - Update `index.html`'s card grid using the same `.post-card`/`.post-tag`
     pattern as the existing entries, matching the tag color you used on the post.
4. **Never claim hands-on testing that didn't happen.** Write from public
   information — pricing, features, platform support — framed as comparison,
   not as "I tested this for 3 months." This is both an honesty issue and a
   ranking-quality issue (search engines increasingly penalize content that
   fakes first-hand experience). This matters even more in security/IT content,
   where readers are making real risk decisions.
5. **Mark affiliate-pending links** with an HTML comment immediately before
   the link, e.g. `<!-- AFF:toolname -->`, and point the `href` at the tool's
   real (non-affiliate) homepage in the meantime. That way the site is fully
   useful and linkable before any affiliate program is approved. See
   "Swapping in real affiliate links" in README.md.
6. **Add AI-answer-engine (GEO/AEO) markup** — required on every post, not optional:
   - `<meta name="author" content="The SMB Security Stack Editorial Team">` and
     a `<link rel="canonical" href="https://REPLACE-WITH-YOUR-DOMAIN/posts/<slug>.html">`
     in `<head>` (swap in the real domain once one exists — grep the repo for
     `REPLACE-WITH-YOUR-DOMAIN` to find every placeholder that needs it).
   - An `Article` JSON-LD block (`headline`, `description`, `author`,
     `publisher`, `datePublished`, `dateModified`) — copy the pattern from
     any existing post.
   - A visible byline with a real `<time datetime="YYYY-MM-DD">` element, not
     just prose text — e.g. `By The SMB Security Stack Editorial Team ·
     Last updated <time datetime="2026-09-21">September 21, 2026</time>`.
   - An `FAQPage` JSON-LD block **plus** a matching visible `<h2>FAQ</h2>`
     section with 3-4 `<h3>` questions and short direct-answer paragraphs.
     Questions should mirror how someone would actually type or speak the
     query to an AI assistant ("Do I need X if I already have Y?"), not
     generic marketing headers. The JSON-LD text and the visible text must
     match — don't put different content in the schema than what's on the page.
   - Don't add `Review` or `AggregateRating` schema — that requires genuine
     ratings/reviews we don't have, and fabricating them is exactly the kind
     of fake-review structured data Google and AI engines actively penalize.
     `Article` + `FAQPage` is the honest, defensible set of schema for this
     site.
7. **Add the post to `index.html`** (top of `.post-list`, most recent first)
   and to `sitemap.xml`.
8. **Commit and push**: `git add -A && git commit -m "Add post: <title>"`.
   If a remote + hosting is connected, this auto-deploys — nothing else needed.

## Topic backlog (rough priority order)

- Best email security / phishing protection add-ons for Google Workspace & Microsoft 365
- Best security awareness training platforms (KnowBe4 vs. Curricula vs. free alternatives)
- Best encrypted file-sharing/cloud storage for sensitive documents (Tresorit vs. Sync.com vs. standard Google Drive/OneDrive)
- Best single sign-on (SSO) providers for small business (Okta vs. JumpCloud vs. Google/Microsoft native SSO)
- Best business-grade firewall/router hardware for a small office
- Best compliance-readiness tools for small business (SOC 2 prep platforms like Vanta/Drata — worth it pre-Series A vs. DIY)

Keep adding to this list as new tools launch or existing ones get replaced —
check it's still accurate before generating from it, since vendor names,
pricing, and positioning shift fast in this space (acquisitions/rebrands are
common — see the Perimeter 81 example above).

## Style notes

- Second person, direct, no filler intros ("In today's fast-paced world of business security...").
- Every post needs the disclosure note near the top, not just in the footer.
- Prefer "check current pricing" language over asserting an exact number
  you're not confident is still accurate.
- Comparison tables first, prose second — readers scan before they read.
- Don't overstate risk or use fear-based framing ("hackers WILL target you")
  to push a sale — it's cheap, it's noticeable, and it undermines trust in a
  security-focused site specifically.
