# Changelog

All notable changes to Lori are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- **Usage dashboard** — Settings → Usage tab with per-agent token totals, activity heatmap, timeseries chart, and session streak stats (Claude Code and OpenCode via native transcript parsing)
- **Opt-in usage telemetry** — anonymous per-agent token aggregate upload when enabled; off by default ([SECURITY.md](SECURITY.md))

## [0.2.0] - 2026-06-25

### Added

- **Vori → Lori rebrand** — product name, bundle ID (`sh.lori`), and user data directory (`~/.lori/lori.db`)
- **Extensions → Apps** — native MCP OAuth for Slack, GitHub, Notion, and other remote MCPs (replaces Composio gateway)
- Session delete confirmation before removing a session and its on-disk history
- Keyboard shortcuts — `⌘,` (Settings), `⌘N` (new session), `⌘K` (focus panel search), `Esc` (close overlay)
- Overlay panel dismiss — header **Back to terminal** / close button and `Esc`
- Sidebar session status legend (collapsible guide for dot meanings)
- Guided terminal empty states with numbered steps and contextual CTAs
- Lori logo in onboarding, collapsed title bar, boot splash, and favicon
- Keyboard focus rings (`:focus-visible`) for interactive elements
- Inline session rename — click the session title in the header (Enter or blur to save, Escape to cancel)
- Tray menu green/yellow status dots and urgency sorting (permission sessions listed first)
- Background-only macOS notifications with click-to-show-and-focus-session
- Antigravity `PreToolUse` hooks for `run_command`, `ask_question`, and `ask_permission` (yellow permission state)
- Onboarding wizard (welcome, appearance, workspace, providers, marketplace)
- User-visible error banners for config load, workspace load, and session-tool discovery failures
- `aria-live` announcements for session status changes

### Changed

- **Breaking:** macOS bundle identifier is now `sh.lori` (installs as a new app identity)
- Agent hook env vars, plugin names (`lori-notify`), and MCP config keys now use the `lori-*` prefix
- Consistent border radii across the UI (removed global zero-radius override)
- Tray session labels now use `{name} — {status}` (e.g. `Ready`, `Needs input`, `Working`) instead of symbol-prefixed status text
- Antigravity permission detection uses official `PreToolUse` matchers instead of treating all pre-tool events as running
- Notifications suppressed when the main window is focused
- Database initialization failure now prevents app launch instead of continuing in a broken state
- Schema migrations propagate errors instead of silently ignoring failures
- `hook-server.json` written with restrictive file permissions on Unix

### Removed

- Composio gateway connections (replaced by per-app MCP OAuth under Extensions → Apps)

### Fixed

- React Doctor issues and modal stacking regression from native `<dialog>` lifecycle
- Antigravity sidebar yellow dot not appearing during permission prompts
- Silent failures when config, workspaces, or session tools failed to load

## [0.1.0] - 2026-06-19

### Added

- Terminal workspace with full PTY sessions (xterm.js)
- Multi-CLI session orchestration for Claude Code, OpenCode, and Antigravity
- Mid-session tool switching with canonical transcript handoff
- Agent lifecycle hooks (running, idle, permission) via local hook server
- Marketplace for MCP plugins (registry search, featured catalog, custom add)
- Marketplace for skills (skills.sh search, featured catalog, custom add/import)
- LLM Providers panel — configure API keys and sync to Claude Code and OpenCode
- Code HUD — turn-scoped git diff panel in the terminal
- IDE deep-links (Cursor, VS Code, JetBrains, and more)
- Settings with theme, default CLI, env vars, and per-agent path overrides
- Hybrid SQLite persistence (`~/.lori/lori.db`)
- macOS menu bar tray with session status glance and background operation
- macOS notifications when a session becomes idle or needs permission
- Hook server shared-secret validation for lifecycle POST requests

### Security

- Provider API keys are masked in the UI (hints only; write-only configure flow)
- Documented local data handling and plaintext secret storage in README

### Changed

- Sidebar session status: green dot when idle, yellow when permission is needed, grey when suspended
- Closing the main window hides to the menu bar instead of quitting
- Background PTYs auto-suspend after 1 minute of idle; running and permission sessions are protected
- OpenCode permission prompts reported via `permission.asked` bus event (not the dedicated hook)

[0.2.0]: https://github.com/loridotsh/lori/releases/tag/v0.2.0
[0.1.0]: https://github.com/loridotsh/lori/releases/tag/v0.1.0
