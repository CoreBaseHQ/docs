# CoreBase Documentation

Source for [docs.corebasehq.com](https://docs.corebasehq.com). Built with [Mintlify](https://mintlify.com).

Anyone can contribute — typo fixes, clarifications, new guides, or full new sections. See [Contributing](#contributing) below.

## Repo layout

```
docs/
├── docs.json                     ← site config: theme, nav, navbar
├── index.mdx                     ← landing page
├── quickstart.mdx
├── concepts/                     ← architecture & security primers
├── platform/                     ← web panel walkthroughs
├── coremcp/                      ← local agent install & config
├── api-reference/                ← Developer API spec
│   ├── endpoints/
│   └── webhooks/
├── images/                       ← screenshots, diagrams
└── logo/                         ← brand marks (light + dark)
```

Pages are MDX (Markdown + JSX). Every page starts with YAML frontmatter:

```mdx
---
title: "Page title"
description: "Short summary shown in search & OG tags."
---

# Body starts here…
```

## Local preview

You'll need Node 18+.

```bash
npm i -g mint          # one time
git clone https://github.com/corebasehq/docs && cd docs
mint dev               # opens http://localhost:3000
```

Pages hot-reload on save. If `mint dev` ever gets stuck, run `mint update`.

## Contributing

### Small fixes (typos, broken links, copy edits)

Easiest path:

1. Open the page on [docs.corebasehq.com](https://docs.corebasehq.com).
2. Click **Edit this page** in the right rail. GitHub opens the source.
3. Make your edit, write a short PR description, submit.

A maintainer reviews and merges, usually within a day.

### Larger changes (new pages, restructured sections)

1. **Open an issue first** — describe the gap and the structure you have in mind. We'll point you at the right home for it before you write much.
2. Fork the repo, create a branch like `docs/billing-faq`.
3. Add or edit `.mdx` files. Use existing pages as a style reference.
4. If you add a new page, register it in `docs.json` under the appropriate `tabs[].groups[].pages` array.
5. Run `mint dev` and click through every page you touched.
6. Run `mint broken-links` — fix any broken hrefs.
7. Open a PR. Reference the issue you opened in step 1.

### What goes in `docs/` vs the main repo

| Belongs here | Belongs in the product repo |
|---|---|
| User-facing how-tos | Internal architecture decisions |
| API surface (request / response) | Implementation details |
| Concepts the customer needs to understand | Internal services, queues |
| Public roadmap | Sprint plans |

If you're unsure, ask in the issue.

## Writing style

A few rules we hold tight to — see [`AGENTS.md`](./AGENTS.md) for the full list.

- **Active voice, second person.** "Run the command", "You can…", not "The command should be run".
- **Sentence case headings.** "Connect a data source", not "Connect A Data Source".
- **Code formatting** for file names, paths, commands, env vars.
- **Bold for UI labels**: Click **Sources → Add agent**.
- **One idea per sentence.** Short paragraphs.
- **Lead with the goal.** Open each section with what the reader is trying to do.
- **Show, don't only tell.** Code samples beat prose every time.

### Components

Mintlify's MDX components are documented at [mintlify.com/docs](https://mintlify.com/docs). The ones we lean on most:

- `<CardGroup>` / `<Card>` — landing pages, cross-links between sections
- `<Steps>` / `<Step>` — numbered procedures
- `<Tip>` / `<Note>` / `<Warning>` — callouts
- `<CodeGroup>` — multi-language code samples

### Images

- Put them in `images/`, reference with `/images/your-image.png`.
- Wrap screenshots in `<Frame>` so they get a border + caption styling.
- Compress before committing — under 200KB if possible.

## Deployment

The `main` branch deploys automatically. PRs get a preview URL once a Mintlify maintainer approves the build.

There is no staging — we ship to docs.corebasehq.com directly on merge. Reverting is a one-line PR if something goes sideways.

## Reporting problems with the docs

Found something confusing, wrong, or missing? Open an issue with:

- The page URL
- What you expected vs. what you found
- (Optional) a suggested fix

We treat doc bugs the same as code bugs.

## License

Documentation is MIT licensed (`LICENSE`). The CoreBase product is governed by the [Terms of Service](https://corebasehq.com/terms).

## Questions

- [hi@corebasehq.com](mailto:hi@corebasehq.com) — anything else
- [@corebasehq on X](https://x.com/corebasehq) — quick async questions
