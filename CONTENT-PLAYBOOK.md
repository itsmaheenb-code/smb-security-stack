# Content playbook

How new posts get added to this site — follow this exactly so every post matches
in structure, tone, and honesty about what is/isn't affiliate-linked. This is
written so either Michelle or a future Claude Code session (manual or scheduled)
can produce a consistent post from it.

## Process for one new post

1. **Pick a topic** from the backlog below (or a new one that fits the same
   pattern: "Best [category of tool] for self-published authors").
2. **Research current facts with web search** — pricing, platform support,
   affiliate program terms (commission, cookie length). Do not reuse numbers
   from an old post without reverifying; software pricing changes often.
3. **Write the post** using `posts/best-book-formatting-software.html` as the
   template: same header/footer, same `.disclosure-note` block near the top,
   a comparison table, one `<h2>` per tool with an honest paragraph, one
   closing "which one should you pick" section addressed to different reader
   situations (budget, platform, use case).
4. **Never claim hands-on testing that didn't happen.** Write from public
   information — pricing, features, platform support — framed as comparison,
   not as "I tested this for 3 months." This is both an honesty issue and a
   ranking-quality issue (search engines increasingly penalize content that
   fakes first-hand experience).
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

- Best cover design tools/services for self-published authors (Canva Pro vs. 99designs vs. hiring a freelance designer)
- Best ARC/reader-magnet delivery tools (BookFunnel vs. StoryOrigin vs. Prolific Works)
- Best wide ebook distributors (Draft2Digital vs. PublishDrive vs. going direct)
- Best Amazon Ads management tools/courses for authors
- Best audiobook production options (ACX vs. Findaway Voices vs. AI narration tools)
- Best author website/newsletter platforms (ConvertKit vs. MailerLite vs. Substack for authors)
- Best beta reader / critique group platforms
- Best print-on-demand options beyond KDP (IngramSpark vs. KDP Print)

Keep adding to this list as new tools launch or existing ones get replaced —
check it's still accurate before generating from it, since the self-publishing
tool landscape moves fast.

## Style notes

- Second person, direct, no filler intros ("In today's fast-paced world of publishing...").
- Every post needs the disclosure note near the top, not just in the footer.
- Prefer "check current pricing" language over asserting an exact number
  you're not confident is still accurate.
- Comparison tables first, prose second — readers scan before they read.
