# Changelog

All notable changes to Lori are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.0] - 2026-06-30

**First release of Lori** — a local desktop control plane for agentic coding on macOS (Apple Silicon).

Lori unifies the AI coding CLIs you already use — Claude Code, Codex, OpenCode, and Antigravity — in one workspace. Configure your MCP servers, skills, and provider keys once, and Lori syncs them into each tool's native format. Move a live conversation from one agent to another without losing context. Everything runs on your machine.

### Highlights

- **One workspace for every agent** — full PTY terminals for Claude Code, Codex, OpenCode, and Antigravity, side by side.
- **Live handoff between tools** — switch a session from one CLI to another mid-conversation through a canonical transcript format.
- **One config plane** — install an MCP plugin, skill, or provider key once; Lori syncs it into each CLI automatically.
- **Lifecycle awareness** — running, idle, and permission states surfaced in the sidebar and macOS menu bar.

### Added

#### Workspace & sessions
- Unified workspace running Claude Code, Codex, OpenCode, and Antigravity with full PTY terminals (xterm.js) and native macOS titlebar integration.
- Session model with create, resume, inline rename, and switching across CLIs without losing context.
- Mid-session tool switching — hand off live conversations between CLIs via a canonical transcript format.
- Per-session git worktrees — each session runs on its own isolated branch; auto `git init` for non-repo folders.
- Onboarding wizard for workspace, appearance, providers, and marketplace setup.

#### Marketplace
- Discover, install, configure, and sync MCP plugins and skills into every supported CLI from a single UI.
- Apps (OAuth MCPs) — connect remote MCP servers (Slack, GitHub, Notion, and more) with native OAuth; no third-party gateway.
- Skill and plugin enable/disable toggles that sync symlinks into each CLI's native directory.

#### LLM providers
- Configure provider API keys once and sync them into each CLI's native config.
- Auto-import and refresh of provider credentials from existing native CLI configs.
- Local inference support, including Ollama (in-app model install) and vLLM.

#### Git & code review
- Changes sidebar (`⌘L`) for stage, commit, push, pull, sync, and in-app PR creation.
- Code HUD — turn-scoped git diff with a syntax-highlighted before/after split view.

#### Usage & telemetry
- Usage dashboard (Settings → Usage) with per-agent token totals, an activity heatmap, and a timeseries chart, sourced from native CLI transcripts.
- Anonymous aggregate usage upload, with opt-out in Settings → Usage.

#### Platform
- Agent lifecycle hooks — running, idle, and permission states via a local hook server and per-CLI notify plugins.
- Menu bar tray with hide-on-close, background PTYs, session glance, and native macOS notifications.
- IDE deep-links to open project folders in Cursor, VS Code, JetBrains, and more.
- In-app auto-updater for signed, notarized releases delivered via the titlebar **Update** button.
- Light and dark themes that follow system preference.
- Keyboard shortcuts — `⌘\` sidebar, `⌘,` Settings, `⌘N` new session, `⌘K` panel search, `⌘L` Changes, `Esc` close overlay.

### Security

- macOS build is signed with an Apple Developer ID and notarized; hardened runtime entitlements allow spawning agent CLIs.
- Local hook server authenticates requests with a shared secret (`X-Lori-Secret` header).
- Provider and MCP credentials are stored locally under `~/.lori/`. They are stored in plaintext in this release; OS Keychain integration is planned.

### Known limitations

- macOS Apple Silicon only.
- Secrets are not yet stored in the OS Keychain.

### System requirements

- macOS 11+ on Apple Silicon (M1 or later).

[Unreleased]: https://github.com/loridotsh/lori
[0.1.0]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.0
