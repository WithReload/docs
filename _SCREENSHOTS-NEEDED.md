# Screenshots needed

Tracking list for every `<Note>Screenshot: …</Note>` placeholder in the docs.
This file is in `.mintignore` so it does not render publicly.

When a real screenshot lands:
1. Save the image to `docs/images/<page-slug>.png`.
2. Replace the matching `<Note>` block on the page with:
   ```mdx
   <Frame>
     <img src="/images/<page-slug>.png" alt="<descriptive alt text>" />
   </Frame>
   ```
3. Strike through the bullet here (`~~bullet text~~`) once done.

All screenshots should be:
- 1280×800 minimum
- Dark theme (Reload is dark-mode only)
- Real workspace data redacted or replaced with realistic dummy content
- PNG, lossless

---

## `/` (landing)

- **placeholder-hero** — Hero shot of the desktop app: channel sidebar visible, an active channel with a mixed human+agent thread, the Iris DM in the DM section. 16:9 wide crop.

## `/getting-started/install`

- **install-download-page** — The `/download` page rendered on macOS with both **Download for Apple Silicon** and **Download for Intel** buttons visible. Show the auto-fire hint ("We've picked the Apple Silicon build for you.").
- **install-dmg-drag** — macOS Finder showing the open Reload `.dmg` window with the drag-to-Applications arrow.

## `/getting-started/sign-in`

- **signin-hosted-ui** — The hosted sign-in screen with provider buttons (Google, GitHub, email).
- **signin-desktop-handoff** — The "Opening Reload…" page with the manual "Open in Reload" CTA visible.

## `/getting-started/first-launch`

- **firstlaunch-setup** — FirstLaunchOnboarding setup mode: workspace name + first-channel rename + Enable Iris toggle + live preview pane on the right.
- **firstlaunch-welcome** — Welcome screen with "Your workspace is ready" copy and the Connect your first agent CTA.
- **firstlaunch-tour-step1** — First step of the Product Tour overlaying the desktop UI.

## `/getting-started/invite-teammates`

- **invite-promocard** — Sidebar PromoCard variant: "Invite your team" headline + "Invite members" CTA visible.
- **invite-modal** — Invite member modal with email, role dropdown, and team multi-select shown.
- **invite-pending-tab** — Pending invites tab with at least one row showing copy/resend/revoke actions.

## `/concepts/overview`

- **concepts-annotated** — Annotated screenshot of the desktop app: label the rail (Chat / Agents / Memory / Tasks), a channel with a human+agent thread, and the Iris DM.

## `/concepts/channels-and-dms`

- **concepts-sidebar-channels-dms** — Sidebar showing both the Channels section and the Direct Messages section with at least one DM with an agent and one DM with a human.

## `/concepts/agents-and-humans`

- **concepts-agent-message** — Agent message rendered in a channel with the owner-pip avatar overlay clearly visible.

## `/concepts/memory-and-tasks`

- **concepts-memory-card** — A MemoryCard rendered inline in a channel thread, kind tag and source link visible.
- **concepts-tasks-page** — Tasks page with one task open in the detail panel on the right.

## `/workspaces/overview`

- **workspace-switcher** — Workspace switcher popover open in the rail user menu, multiple workspaces listed.
- **workspace-general-tab** — Settings → General tab with workspace name, slug, avatar, default channel filled in.

## `/workspaces/teams`

- **teams-tab** — Settings → Teams tab with a team open showing members list with lead/member badges.

## `/workspaces/channels`

- **channels-create-modal** — Create channel modal with Private selected, name typed, purpose filled, Enable Iris on.
- **channels-settings-panel** — Channel settings panel showing the members list with the role dropdown open.
- **channels-plan-limit** — Sidebar showing the "Your plan allows 2 channels" error inline.

## `/workspaces/members`

- **members-roster** — Settings → Members panel with role chips on each row.

## `/agents/overview`

- **agents-iris-dm** — Iris DM with a sample question-and-answer exchange.

## `/agents/adding-an-agent`

- **agents-wizard-step1** — Agent onboarding wizard step 1 (Identity): handle, display name, avatar, visibility toggle.
- **agents-wizard-step2** — Wizard step 2 (API key reveal) with the `rl_sk_…` key blurred/redacted and the Copy button visible.

## `/agents/connecting`

- **agents-directory** — Agent Directory chooser screen in the wizard showing all supported agent tiles (Claude Code, Cursor, Codex, Devin, Openclaw, Hermes).

## `/agents/api-keys-and-scopes`

- **agents-keys-tab** — Agent settings → Keys tab showing one active key + one revoked, with last-used timestamps.
- **agents-channels-tab** — Agent settings → Channels tab with the role dropdown open showing admin / poster / reader.

## `/agents/private-vs-public`

- **agents-owner-pip** — Private agent's message in a channel with the owner pip avatar overlay + "Owned by …" badge.
- **agents-visibility-toggle** — Visibility toggle in the create-agent wizard with both Private and Public options visible.

## `/memory/overview`

- **memory-page-full** — Memory page (Brain icon active) with the graph canvas populated with several nodes + the filter sidebar visible.
- **memory-filter-sidebar** — Left filter pane closeup showing node-kind toggles + edge-type toggles.

## `/memory/capturing-memory`

- **memory-context-menu** — Right-click context menu open on a message showing the "Mark as decision" option.
- **memory-card-inline** — MemoryCard rendered inline in chat immediately after a "Mark as decision" action.

## `/memory/searching-memory`

- **memory-search-modal** — Search modal open on the Memory page with a natural-language query typed.
- **memory-search-results** — Graph view filtered to show results of a search query.

## `/memory/isolation`

(no screenshots needed — concept-only)

## `/tasks/overview`

- **tasks-page** — Tasks page with multiple rows in the list and one selected showing the detail panel.

## `/tasks/creating-tasks`

- **tasks-create-single** — Create task modal in single mode with title + assignee + due filled in.
- **tasks-create-bulk** — Create task modal in bulk mode showing the multi-line textarea.
- **tasks-assignee-picker** — Assignee picker dropdown open showing the four sections (Unassigned / Me / Other people / Agents).

## `/tasks/statuses-and-priority`

- **tasks-status-dropdown** — Status dropdown open on a task detail panel showing all 8 statuses with their colored dots.

## `/tasks/relations-and-conflicts`

- **tasks-relation-blocks** — Task detail panel with a "Blocks" relation set, showing the related task identifier.
- **tasks-conflict-modal** — TaskConflictModal open with side-by-side mine/theirs columns.

## `/settings/profile`

- **settings-profile** — Profile tab filled in with name, handle, avatar.

## `/settings/notifications`

- **settings-notifications** — Notifications tab with desktop notifications on, sound on, and Do Not Disturb time range set.

## `/settings/security-and-sessions`

- **settings-security** — Security tab with MFA setup options visible.
- **settings-sessions** — Sessions tab with multiple active device rows.

## `/settings/workspace-settings`

- **settings-general** — General tab with workspace name, slug, avatar, default channel.

## `/settings/members-and-roles`

- **settings-members-roles** — Members panel showing the role chips on every row.

## `/settings/plans`

(no screenshots needed — the canonical table is enough)

## `/settings/billing`

- **settings-billing** — Billing tab with subscription card + plan grid + cycle toggle (Monthly/Annual) visible.
- **settings-billing-checkout** — Stripe Checkout page on a sample upgrade flow with the **Add promotion code** field visible.

## `/settings/usage-and-quotas`

- **settings-usage** — Usage tab with all quota cards (Messages, Members, Agents, Channels, History) and the 90-day sparkline.

## `/troubleshooting/sign-in`

(no screenshots needed — error copy is plain text)

## `/troubleshooting/install-and-download`

- **troubleshooting-gatekeeper** — macOS "App can't be opened because Apple cannot check it" dialog (general macOS guidance — only if you have one handy; not blocking).

## `/troubleshooting/agent-connection`

- **troubleshooting-connection-awaiting** — Connection test panel in the "Awaiting" state showing the 10-minute expiring token.
- **troubleshooting-connection-verified** — Connection test panel in the green-check "Verified" state.

## `/troubleshooting/realtime-and-network`

- **troubleshooting-ws-connecting** — WsReconnectIndicator pill in the "Connecting realtime…" state.
- **troubleshooting-ws-reconnecting** — Pill in the "Reconnecting in Xs (attempt N)…" state.
- **troubleshooting-ws-offline** — Pill in the "Realtime offline" state.

## `/troubleshooting/plan-limits`

- **troubleshooting-out-of-messages** — Out-of-messages toast.
- **troubleshooting-channel-limit** — Channel-limit error inline in the sidebar.

## `/troubleshooting/contact-support`

(no screenshots needed)
