# Reload Documentation — project instructions

This is the user-facing product documentation for Reload, hosted on Mintlify and
served at the docs subdomain. It is **not** a developer/API reference and it
**must not** expose internal stack details.

## About this project

- Mintlify-based docs site.
- Pages are MDX files with YAML frontmatter.
- Configuration lives in `docs.json`.
- Run `mint dev` to preview locally; `mint broken-links` before opening a PR.

## Terminology

Use these terms exactly. They match what users see in the product.

- **Workspace** — the top-level container. Every user has at least one.
- **Channel** — where conversations happen. Public or private. Has roles
  (`admin`, `poster`, `reader`).
- **Direct message (DM)** — one-to-one conversation between any two workspace
  members (human or agent).
- **Member** — a human in a workspace. Roles: `owner`, `admin`, `member`,
  `guest`.
- **Team** — a subgroup of workspace members. Roles: `lead`, `member`. Used to
  grant channel roles in bulk and for `@team` mentions.
- **Agent** — an AI participant in the workspace. Has a `@handle`, an avatar,
  channel memberships, and a role just like a human.
- **Iris** — the built-in agent every workspace ships with. User-facing name;
  use it.
- **Memory** — Reload's long-term shared brain. Captures decisions, facts, and
  preferences. Lives on the Memory page (Brain icon in the rail).
- **Task** — a unit of work in the Tasks page. Has a status, priority,
  assignee, and optional channel binding.
- **Plan** — one of: Starter, Individual, Pro, Growth, Custom.

## Voice and style

- Active voice, second person ("you").
- One idea per sentence. Short sentences win.
- Sentence case for headings.
- Bold for UI elements you click: "Click **Settings**".
- Code formatting for file names, commands, paths, and any literal string a
  user types or sees as code.
- Match exact in-product copy when quoting. If a button reads "Add an agent",
  don't paraphrase it as "Add agent".

## Content boundaries — strict

Never expose any of the following in published pages:

- Internal stack names: framework names (the database, the graph engine, the
  job queue, hosting providers), schema field names, table names.
- Internal codenames except **Iris** (Iris is user-facing — the engine that
  powers Memory is not).
- Repository layout, file paths, internal APIs, MCP transport internals,
  RBAC/ACL resolver logic, feature flag names, environment variable names.
- "Open source" / OSS language. Reload is a commercial product.
- Stripe price IDs, webhook details, customer ID storage, JWT internals.
- Audit log internals, rate-limit dispatch internals, error codes
  (`AUTH_INVALID_API_KEY` etc. — quote the user-visible copy instead).

If a feature is built but feature-flagged off in V1 (Skills tab, Referrals tab,
Triggers, Knowledge Base, topup packs, workspace switching button, etc.),
**don't document it.** Only document what ships.

## Grounding rule

Every factual claim in a page traces back to a specific file in the Reload
product repo. When writing, include the source file:line in a hidden HTML
comment immediately above the claim so a reviewer can verify:

```mdx
{/* source: apps/desktop/src/components/sidebar/ChannelSidebar.tsx:174 */}
"Your plan allows 2 channels. Upgrade to add more."
```

These comments are stripped from the rendered page. They exist for the next
agent or human who needs to fact-check the docs.

## Screenshot placeholder pattern

When a page needs an image you don't have yet, use this exact pattern:

```mdx
<Note>
  **Screenshot:** *Description of what should appear here.* Coming soon.
</Note>
```

Then add an entry to `_SCREENSHOTS-NEEDED.md` (mintignored) with:
- The page slug
- What to capture (UI region, state, copy visible)
- Aspect / frame notes

Real screenshots eventually land in `images/<page-slug>.png` and the `<Note>` is
swapped for:

```mdx
<Frame>
  <img src="/images/<page-slug>.png" alt="<descriptive alt text>" />
</Frame>
```

## Linking conventions

- Internal links use relative paths without the `.mdx` extension:
  `[Install Reload](/get-started/install)`.
- External links open in a new tab (Mintlify handles this automatically).
- Cross-section links at the bottom of get-started pages form a linear flow
  (install → sign-in → first-launch → invite-teammates).

## Mintlify components in active use

- `<Card>`, `<CardGroup>` — landing pages and section indexes.
- `<Tabs>`, `<Tab>` — multi-client setup pages (agent connecting page).
- `<Note>`, `<Warning>`, `<Tip>`, `<Info>` — callouts.
- `<AccordionGroup>`, `<Accordion>` — long reference pages where users only
  want one section at a time.
- `<Frame>` — wrapping screenshots once they're added.

## What not to add

- Don't add new top-level sections without a docs.json update + reviewer signoff.
- Don't add documentation files outside of `docs/` (root MDX is reserved for `index.mdx`).
- Don't link to dashboards, status pages, or third-party services that don't
  exist yet. If a user-visible link in the product needs documenting and the
  service isn't live, leave a `<Note>` placeholder, not a broken link.
