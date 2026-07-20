# Changelog

All notable changes to Lori are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.4.11] - 2026-07-20

Richer prompt composer slash commands and real media previews in the Files panel.

### Added

- **Slash command palette** — type `/` in the prompt composer to insert agent CLI commands (Claude, Codex, OpenCode, Antigravity, Hermes, Cursor), ranked like `@` file mentions.
- **Skills in `/` menu** — enabled marketplace skills for the active agent show up alongside built-in commands, so you can insert `/skill-name` without leaving the composer.
- **Media previews** — the Files panel previews images, video, audio, and PDFs instead of showing binary placeholders.

### Changed

- **Slash catalogs** — per-agent command lists expanded to match current CLI docs, with fuller coverage for every supported agent.

## [1.4.10] - 2026-07-19

A richer prompt bar with @ file mentions, clearer marketplace and Ollama flows, and a handful of everyday reliability fixes.

### Added

- **Prompt composer** — a Warp-style input under agent terminals for multi-line messages (Enter to send, Shift+Enter for a new line), with drafts that stick around when you switch panes.
- **@ file mentions** — type `@` in the composer to search and insert workspace files as chips; toggle in Settings → Sessions.
- **Marketplace restart banner** — after you install or toggle an extension, tabs that need a restart show an in-tab “Restart now” prompt so the agent picks up the new config.
- **Status bar toggle** — Settings → Sessions can hide the terminal status strip if you want a cleaner bottom edge.

### Changed

- **Extensions library** — sturdier install/configure paths and clearer library browsing for apps, plugins, and memory tools.
- **Ollama model picking** — clearer installed-model selection when wiring Ollama in Connections.
- **Quit and resume copy** — quit confirmation explains that sessions and history are saved; suspended sessions say “Click to resume.”

### Fixed

- **Changes after agent turns** — git status in the Changes sidebar refreshes when an agent finishes a turn, so new edits show up without a manual refresh.
- **Claude provider switch** — switching Claude to another provider still works when the previous gateway’s API key was cleared.
- **OAuth reconnect** — abandoning a connect flow no longer leaves the callback port stuck for the next attempt.

## [1.4.9] - 2026-07-15

Smoother everyday use — easier folder access after restart, clearer agent switching, cleaner theming, and a few quality-of-life upgrades in the terminal and marketplace.

### Added

- **Re-authorize folder** — if macOS blocks a workspace after reboot (Desktop, Documents, and similar), Lori shows a clear fix: re-authorize the folder from the sidebar or Files panel without losing your sessions.
- **Terminal status bar** — a compact status strip under the terminal with useful session context, plus a review affordance in the titlebar when you have changes to look at.
- **Links open in Lori** — click a URL in the terminal and it opens in Lori’s built-in browser tab instead of bouncing you out to another app.

### Changed

- **Agent switcher** — only agents installed on your machine show up when you switch or replace an agent, so you aren’t offered tools you can’t run.
- **Marketplace Explore** — clearer browsing when discovering apps, plugins, and skills.
- **Files panel** — the file tree stays in sync as files change on disk.
- **Snappier sessions** — switching sessions, opening tabs, and everyday git/UI actions feel more responsive.
- **Color system** — semantic colors now use OKLCH for more consistent themes across light and dark Graphite, including the terminal.

### Fixed

- **Codex hand-off** — continuing a conversation from Codex into another coding agent keeps more of the prior chat, so the next agent isn’t starting from a blank slate.
- **Workspace access after Mac restart** — Lori no longer treats a blocked folder as “not a workspace”; you get a clear message and a path to restore access.
- **Claude session titles** — sessions that start with a local slash command no longer pick up the internal “Caveat…” harness text as their title.
- **OAuth app card** — connected-app fallback styling follows the active theme instead of a hardcoded indigo.
- **Model download progress** — Ollama download progress animates more smoothly without jank.

## [1.4.8] - 2026-07-12

More reliable connected apps in Hermes, and a cleaner Connections list.

### Fixed

- **Hermes connected apps** — authenticated MCP apps (Cloudflare, Notion, Canva, Hugging Face, and others) now send credentials correctly, so their tools load instead of failing to connect.

### Changed

- **Codex with local models** — choose which Ollama or vLLM model Codex uses from Connections, the same way you can for other providers.
- **Connections list** — provider rows show assigned agents as icons only, without repeating their names in the subtitle.

## [1.4.7] - 2026-07-11

Better provider support across Codex and Hermes.

### Added

- **Codex model picker** — choose which model Codex uses per provider in Connections, the same way you configure Claude.

### Changed

- **Custom providers for Hermes** — your custom OpenAI and Anthropic endpoints now sync into Hermes automatically instead of being skipped.
- **Provider settings copy** — clearer wording that applies to all agents, not just OpenCode.
- **Custom provider icons** — custom providers use the Lori mark for a more consistent look in Connections.

## [1.4.6] - 2026-07-11

Easier project setup and polish across onboarding and the sidebar.

### Added

- **Welcome actions** — open an existing folder, create a new project, or clone a repo right from the empty workspace screen.
- **Markdown preview** — view rendered markdown in the file viewer with a Preview / Raw toggle.

### Changed

- **Onboarding** — refreshed welcome flow with the Lori mark, real agent icons, and ⌘⏎ to continue on every step.
- **Menu bar icon** — Lori now uses the mark in the macOS menu bar.
- **Sidebar and syntax** — tidier hover states and shortcut hints; improved code highlighting in light mode.

## [1.4.5] - 2026-07-11

A refreshed sidebar, built-in browsing, and a smoother experience throughout Lori.

### Added

- **Browser tab** — open a web page right inside Lori alongside your agents and terminals, with back, forward, reload, and URLs that stick around when you come back.

### Changed

- **Sidebar layout** — Workspaces are now at the top so your projects and sessions are front and center; Extensions, Skills, Automations, and Connections sit at the bottom.
- **Cleaner look** — softer borders in the sidebar and Changes panel, and the titlebar flows into the sidebar as one surface.
- **Extensions** — easier to browse and spot what you can install, with nicer loading and empty states when a library is empty.
- **Welcome screen** — clearer prompts when you're getting started, including which agents Lori found on your machine.

### Fixed

- **Browser navigation** — fixed a crash that could happen when moving between pages in a browser tab.

## [1.4.4] - 2026-07-10

A cleaner, more consistent look across Lori.

### Changed

- **Buttons and alerts** — primary actions are easier to spot, and dialogs and notices feel more consistent everywhere you work in Lori.
- **Typography and color** — small labels and metadata are easier to read; accent colors look more cohesive across Automations, Changes, Marketplace, and Settings.

### Fixed

- **Dialog close button** — fixed a distracting highlight on the × button when a dialog first opens on macOS.

## [1.4.3] - 2026-07-09

### Added

- **What's New modal** — after updating Lori, a one-time changelog modal highlights what changed in the new version.

### Changed

- **OAuth success page** — the browser callback page after connecting an app now matches Lori's dark Graphite styling.

## [1.4.2] - 2026-07-09

Marketplace Apps expansion and faster Extensions loading.

### Added

- **More Apps in Extensions** — expanded catalog of remote MCP apps (Amplitude, ClickUp, Cloudflare, Context7, Dropbox, Exa, Heroku, Hugging Face, Miro, Plaid, PostHog, Prisma, Railway, Semgrep, Supabase, Wix, and more) with icons in the marketplace.

### Changed

- **Extensions list loads faster** — the Apps list no longer blocks on OAuth discovery probes while browsing; connection still validates when you connect an app.

### Fixed

- **Linux release builds** — remote AppImage fetch after Docker builds no longer fails due to a broken SSH listing command.

## [1.4.1] - 2026-07-08

Safer tab closes with clearer confirmation copy.

### Added

- **Close tab confirmation** — closing an agent or terminal tab now asks before tearing down the session, so a live agent or shell is not lost by accident.

### Changed

- **Close tab dialog** — clearer titles and messages for agent vs terminal tabs, including when a process is still active.

## [1.4.0] - 2026-07-08

Automations and Cursor join the workspace, with polish across the new Automations experience.

### Added

- **Automations** — run a coding agent task in an isolated git worktree, on demand or on a schedule. Open **Automations** from the sidebar to create jobs, pick a workspace and agent (Claude, Codex, or OpenCode), write an instruction, and choose **Manual** or **Schedule** (hourly, daily, weekly, or custom cron).
- **Automation controls** — set sandbox level (read-only, propose changes, or full write), optional base branch, max runtime, and concurrent run limits. Pause, resume, run now, or cancel in-flight runs from the list or detail view.
- **Automation run history** — each automation has a run log with live status (queued, running, needs permission, succeeded, failed, timed out). Open a run to see duration, branch, exit code, raw output, and a formatted **agent summary** when the CLI provides one.
- **Cursor** — run the Cursor Agent CLI in Lori alongside your other tools. Start and resume sessions, switch tabs like any other agent, and see when it's working, idle, or waiting on you.
- **Extensions and skills for Cursor** — marketplace installs sync into Cursor the same way they do for your other agents.
- **Cursor usage tracking** — token usage from Cursor runs appears in Settings → Usage when the agent reports it.

### Changed

- **Sidebar navigation** — **Automations** sits alongside Extensions, Skills, and Connections with a cleaner, divider-free nav. Re-clicking **Automations** returns you to the list when you're viewing a detail screen.
- **Automation form** — agent picker shows CLI icons; schedule setup uses clearer hour, minute, and weekday controls instead of raw cron by default.
- **Automation run results** — summaries render as formatted markdown in a resizable right sidebar instead of a modal, with a tidier toolbar for **Active** and **Run now**.
- **Overlay behavior** — opening a session from the sidebar closes Automations, and session highlighting clears while a full-panel overlay is open so the UI doesn't look like two places are active at once.
- **Non-git workspaces** — automations run in the project folder when a workspace isn't a git repo.

### Fixed

- **Codex automations** — unattended Codex runs no longer fail with an unexpected-argument error.
- **Cursor permission indicator** — the sidebar correctly shows when Cursor is waiting on shell or MCP approval.

## [1.3.1] - 2026-07-06

Polish for in-app updates and agent status at a glance.

### Changed

- **Update button** — when an update is available, the titlebar control is now a compact blue button that’s easier to spot.
- **Agent status** — running agents use a clearer spinner; permission prompts use a brighter amber pulse so “needs input” stands out from idle grey.

## [1.3.0] - 2026-07-06

Hermes joins the workspace, and Connections works better with more providers.

### Added

- **Hermes** — run Hermes in Lori alongside your other coding tools. Open and resume Hermes sessions, switch tabs like any other agent, and see when it’s working, idle, or waiting on you.
- **Providers for Hermes** — enable your LLM providers for Hermes in Connections; Lori keeps credentials in sync so you don’t have to copy keys by hand.
- **Extensions and skills** — marketplace installs sync into Hermes the same way they do for your other agents.
- **Easier first-time setup** — if you already use Hermes on its own, Lori can import your existing provider setup when you open Connections.

### Fixed

- **Claude Code on Groq and similar providers** — the Claude Code option and **Translated** label show again on OpenAI-style providers where Lori bridges requests locally.

## [1.2.0] - 2026-07-04

Linux support, simpler custom provider setup, and broader compatibility across agents.

### Added

- **Linux support** — Lori is now available on Linux alongside macOS. Download the AppImage, make it executable, and run it. In-app updates work after the first AppImage install.
- **Simpler custom providers** — add a provider with a single URL; Lori detects how to connect automatically.
- **Cross-agent provider routing** — use more custom endpoints with Claude, Codex, and OpenCode without manual setup for each combination.

### Changed

- Custom provider setup uses one URL field instead of separate connection-type choices.
- Clearer experience when pairing custom providers with Claude.

### Fixed

- Custom provider routing stays correct when Lori cannot infer the connection type from the URL alone.

### Platform notes

- **macOS** — Apple Silicon with in-app updates.
- **Linux** — x86_64 AppImage with in-app updates. Users on the legacy bare binary should switch to the AppImage once.
- **Windows** — not supported yet.

## [0.1.3] - 2026-07-03

Faster Changes sidebar, smarter branch switching, and clearer git actions in History.

### Added

- **Branch switch preflight** — before switching branches, Lori checks for conflicting uncommitted files and lets you bring everything along or remove only the conflicting paths.
- **Update from main** in History — on a feature branch in a shared session, pull the latest `main` into your branch without needing a remote tracking branch first.

### Changed

- **Changes file list** stays responsive with thousands of changed files.
- History **Push** and **Pull** show counts against your branch’s remote (`origin`), not misleading numbers vs `main`.
- History git actions are disabled when you’re only *viewing* another branch’s commits — switch to that branch in Changes first.

### Fixed

- Branch switching no longer fails silently on untracked files that would block checkout.
- Lori-owned stash entries are restored safely after a branch switch, with clear messaging if something needs your attention.

## [0.1.2] - 2026-07-03

Branch management and safer quit flow in the Changes sidebar.

### Added

- **Branch picker** in the Changes sidebar — switch to an existing branch or create a new one from the branch badge. Uncommitted changes are preserved when you switch.
- **Quit confirmation** — Lori asks before closing when you have active sessions, so a stray ⌘Q doesn't end your work.

### Changed

- Agent tab label updated from "Claude Code" to **Claude**.
- Refined branch picker and quit dialog styling for clearer actions in light and dark mode.
- Quit dialog shows how many active sessions will be closed.

### Fixed

- Switching to a branch that only exists on the remote now works from the branch picker.
- Creating a new branch from the picker is more reliable.
- Branch-switch warnings (e.g. when restoring your changes needs attention) are shown as notices instead of errors.

## [0.1.1] - 2026-07-02

Patch release with keyboard shortcut improvements, sidebar polish, and git status fixes since v0.1.0.

### Added

- **⌘1–⌘9** shortcuts to switch agent tabs in the active session (display order).
- Terminal find/search support via `@xterm/addon-search`.

### Changed

- Frontend design polish — motion, copy, design tokens, and signature styling.
- Workspace sidebar alignment, symmetry, and selection states.
- Session dialogs and git status refresh performance in the sidebar.

### Fixed

- **⌘N** (new session) works while the terminal (xterm) has focus.
- Git status parsing for renamed and quoted porcelain paths in the Changes sidebar.
- Agent lifecycle hooks transition from permission to running after `PostToolUse`.
- TypeScript errors that blocked production builds.

## [0.1.0] - 2026-07-01

**First release of Lori** — a local desktop control plane for agentic coding on macOS (Apple Silicon).

Lori unifies the AI coding CLIs you already use — Claude Code, Codex, OpenCode, and Antigravity — in one workspace. Configure your MCP servers, skills, and provider keys once, and Lori syncs them into each tool's native format. Move a live conversation from one agent to another without losing context. Everything runs on your machine.

### Highlights

- **One workspace for every agent** — full PTY terminals for Claude Code, Codex, OpenCode, and Antigravity, side by side.
- **Live handoff between tools** — switch a session from one CLI to another mid-conversation through a canonical transcript format.
- **One config plane** — install an MCP plugin, skill, or provider key once; Lori syncs it into each CLI automatically.
- **Lifecycle awareness** — running, idle, and permission states surfaced in the sidebar and macOS menu bar.
- **Full git workflow in-app** — VS Code-style right sidebar with nested file tree, turn-scoped diffs, commit history graph, and commit viewer.
- **Flexible provider routing** — per-agent provider assignment, dual-route gateways, and local inference via Ollama and vLLM.

### Added

#### Workspace & sessions
- Unified workspace running Claude Code, Codex, OpenCode, and Antigravity with full PTY terminals (xterm.js) and native macOS titlebar integration.
- Session model with create, resume, inline rename, restart tab, and switching across CLIs without losing context.
- Mid-session tool switching — hand off live conversations between CLIs via a canonical transcript format.
- Per-session git worktrees — each session can run on its own isolated branch; auto `git init` for non-repo folders. Default isolation mode is **shared** (opt into worktree isolation per session or in Settings).
- Per-agent launch arguments in Settings — pass custom flags to each CLI on session start.
- Onboarding wizard for workspace, appearance, providers, and marketplace setup.
- Optional onboarding email signup for Lori account and product updates (stored locally after server ack).

#### Right sidebar & git
- VS Code-style right sidebar (`⌘L`) with **Changes**, **Files**, and **History** tabs.
- Nested file tree in the Changes sidebar for browsing staged and unstaged files.
- Turn-scoped Code HUD — syntax-highlighted before/after split diff view in the Changes "This turn" tab.
- Git history graph with commit list, filters, and a commit detail viewer.
- Full git workflow — stage, unstage, commit, push, pull, sync, and in-app PR creation (via `gh`).
- Differentiated Changes and History UX for worktree-isolated vs shared sessions.
- Session title breadcrumb with path-style branch context in the header.

#### Marketplace
- Discover, install, configure, and sync MCP plugins and skills into every supported CLI from a single UI.
- Apps (OAuth MCPs) — connect remote MCP servers (Slack, GitHub, Notion, and more) with native OAuth; no third-party gateway.
- Skill and plugin enable/disable toggles that sync symlinks into each CLI's native directory.
- In-app Ollama install and live hardware-gated model library.

#### LLM providers
- Configure provider API keys once and sync them into each CLI's native config.
- Auto-import and refresh of provider credentials from existing native CLI configs.
- Per-row provider assignment — toggle which agents each provider routes to, with native OpenCode slot support.
- Custom dual-route providers with searchable model pickers (Fireworks, Claude Code gateways, and custom endpoints).
- Multi-slot OpenCode import with active CLI indicators.
- Bundled providers including Anthropic, OpenAI, Google, Ollama, vLLM, Venice AI, and AkashML.
- Local inference support via Ollama (in-app model install) and vLLM (venv-aware detection).

#### Usage & telemetry
- Usage dashboard (Settings → Usage) with per-agent token totals, an activity heatmap, timeseries chart, and session streak stats — sourced from native CLI transcripts.
- Product analytics panels and improved telemetry dashboard metrics.
- Anonymous aggregate usage upload, on by default with opt-out in Settings → Usage.
- Token usage preserved when sessions or workspaces are removed.

#### Platform & settings
- Agent lifecycle hooks — running, idle, and permission states via a local hook server and per-CLI notify plugins; expanded per-agent hook coverage for lifecycle and Code HUD refresh.
- Menu bar tray with hide-on-close, background PTYs, session glance, and native macOS notifications.
- IDE deep-links to open project folders in Cursor, VS Code, JetBrains, and more.
- In-app auto-updater for signed, notarized releases delivered via the titlebar **Update** button.
- Light and dark themes that follow system preference, with full light-mode variants and a font smoothing toggle in Appearance settings.
- About settings tab with version info and worktree base branch configuration.
- Keyboard shortcuts — `⌘\` sidebar, `⌘,` Settings, `⌘N` new session, `⌘K` panel search, `⌘L` right sidebar, `Esc` close overlay.

### Changed

- Replaced violet accent theme with neutral graphite styling; toned-down dark mode with brighter text for clearer contrast.
- Redesigned sidebar agent rows — flat indent, stable status column, git context, and diff stats on session items.
- Redesigned Providers settings with macOS grouped layout, polished modals, and per-row agent controls.
- Default sidebar width set to 220px.
- Title bar is read-only; window dragging works via the native chrome.
- Disabled web-style text selection on app chrome and browser context menu / reload shortcuts in production builds.
- Speed up Changes sidebar and diff review with instant previews and virtualized code lines.
- Simplified worktree Changes header to a compact single row.
- Workspace chevron shown on hover instead of by default.

### Fixed

- Git workflow correctness in the Changes sidebar — fresh repos, untracked folders, stage/commit/push edge cases.
- Code HUD — preview new (untracked) files and reduced diff-panel latency.
- Claude Code token tracking for worktree and shared sessions.
- Antigravity lifecycle flicker — no longer idles on `PostInvocation`.
- Sidebar session indicators for suspended and unloaded sessions.
- Black screen when closing a fullscreen window on macOS.
- Terminal copy on Linux — selections written to the native clipboard when WebKitGTK does not emit a copy event.
- Dual-route provider models, OpenCode import, and Claude model mapping combobox issues.
- Agent switch menu opening unexpectedly when changing tabs.
- Skills explore list flashing on install.
- Telemetry uploads when install ID was never persisted.
- Workspace open/read permission issues.
- VirtualizedCodeLines viewport height initialization on mount.
- macOS tray icon rendering and pre-release UI pattern inconsistencies.

### Security

- macOS build is signed with an Apple Developer ID and notarized; hardened runtime entitlements allow spawning agent CLIs.
- Local hook server authenticates requests with a shared secret (`X-Lori-Secret` header).
- Security audit hardening across the desktop app and telemetry server — fail-closed auth in production, restricted marketplace/OAuth/git attack surfaces, path traversal protections, and safe URL handling in the UI.
- Provider and MCP credentials are stored locally under `~/.lori/`. They are stored in plaintext in this release; OS Keychain integration is planned.

### Known limitations

- macOS Apple Silicon only (Linux fixes are in-tree for future ports).
- Secrets are not yet stored in the OS Keychain.

### System requirements

- macOS 11+ on Apple Silicon (M1 or later).

[Unreleased]: https://github.com/loridotsh/lori/compare/v1.4.1...HEAD
[1.4.1]: https://github.com/loridotsh/lori-updates/releases/tag/v1.4.1
[1.4.0]: https://github.com/loridotsh/lori-updates/releases/tag/v1.4.0
[1.3.1]: https://github.com/loridotsh/lori-updates/releases/tag/v1.3.1
[1.3.0]: https://github.com/loridotsh/lori-updates/releases/tag/v1.3.0
[1.2.0]: https://github.com/loridotsh/lori-updates/releases/tag/v1.2.0
[0.1.3]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.3
[0.1.2]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.2
[0.1.1]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.1
[0.1.0]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.0
