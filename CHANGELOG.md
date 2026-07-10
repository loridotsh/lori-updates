# Changelog

All notable changes to Lori are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.4.4] - 2026-07-10

UI polish across the Graphite theme.

### Changed

- **Primary actions** — clearer call-to-action styling on Graphite with a dedicated interactive accent token; shared `Button` and `Alert` components replace one-off styles across the app.
- **Design tokens** — metadata text is floored at 11px for readability; hardcoded amber and blue accents are replaced with semantic tokens throughout Automations, Changes, Marketplace, and Settings.

### Fixed

- **Modal close button** — the X no longer shows a focus ring when a dialog first opens on macOS.

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
