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
   as the template: same header/footer, same `.disclosure-note` block near the
   top, a comparison table, one `<h2>` per tool with an honest paragraph, one
   closing "which one should you pick" section addressed to different reader
   situations (team size, budget, technical sophistication).
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
6. **Add the post to `index.html`** (top of `.post-list`, most recent first)
   and to `sitemap.xml`.
7. **Commit and push**: `git add -A && git commit -m "Add post: <title>"`.
   If a remote + hosting is connected, this auto-deploys — nothing else needed.

## Topic backlog (rough priority order)

- Best endpoint protection / antivirus for small business (Malwarebusiness vs. CrowdStrike Falcon Go vs. Microsoft Defender for Business)
- Best email security / phishing protection add-ons for Google Workspace & Microsoft 365
- Best MFA/2FA solutions for small teams (Duo vs. built-in authenticator apps vs. YubiKey hardware keys)
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
