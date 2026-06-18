> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## Terminology

- CoreBase is a **governed agent platform for enterprise data** — lead with agents (autonomous + proactive + multi-step flows). Legacy/on-prem/air-gap **reach** is the moat (why it's defensible), not the headline.
- Use **"Unified Context"** or **"Query Memory"**, not "Corporate Memory".
- Use **"agent" / "agent flow" / "step"**, not "workflow automation" generically. A flow is a DAG of trigger → agent/action nodes.
- **"data-sovereign" / "network-safe"**, never "local-first".
- CoreMCP = the open-source, on-prem, zero-trust bridge (sovereign tier). Nango-backed SaaS connectors = cloud-relay tier. Keep the two tiers distinct.
- Be honest about status: approval gates/budgets/kill-switch, notify actions, event-subtype filtering, and SaaS RAG ingestion are **roadmap** — mark them as such, don't imply they ship today.

## Style preferences

<!-- Add any project-specific style rules below -->

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

<!-- Define what should and shouldn't be documented -->
<!-- Example: Don't document internal admin features -->
