# Changelog

All notable changes to Lori are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.0.1] - 2026-06-28

Test release to validate the `loridotsh/lori-updates` publish pipeline (updater artifacts + `.dmg`).

## [0.1.0] - 2026-06-28

First public beta for **macOS Apple Silicon**. Download from [GitHub Releases](https://github.com/loridotsh/lori-updates/releases/tag/v0.1.0). In-app updates via the titlebar **Update** button.

### Added

- **Unified agent workspace** — run Claude Code, OpenCode, Codex, and Antigravity from one desktop app with full PTY terminals (xterm.js)
- **Mid-session tool switching** — hand off live conversations between CLIs via a canonical transcript format
- **Marketplace** — discover, install, and sync MCP plugins and skills into every supported CLI from one UI
- **Apps (OAuth MCPs)** — connect remote MCPs (Slack, GitHub, Notion, and more) with native OAuth; no third-party gateway
- **LLM Providers** — configure API keys once and sync into each CLI’s native config
- **Agent lifecycle hooks** — running, idle, and permission states in the sidebar and macOS menu bar via a local hook server
- **Session git worktrees** — optional per-session isolation on its own branch; Changes sidebar (`⌘L`) for stage, commit, push, pull, sync, and PR creation
- **Code review in Changes** — turn-scoped git diff with syntax highlighting
- **Usage dashboard** — Settings → Usage with per-agent token stats, heatmap, and chart (from native CLI transcripts)
- **In-app auto-updater** — signed updates from [loridotsh/lori-updates](https://github.com/loridotsh/lori-updates) releases
- **Onboarding wizard** — workspace, appearance, providers, and marketplace setup
- **Menu bar tray** — hide-on-close, background PTYs, session glance, and macOS notifications
- **IDE deep-links** — open project folders in Cursor, VS Code, JetBrains, and more
- **Keyboard shortcuts** — `⌘,` Settings, `⌘N` new session, `⌘K` panel search, `⌘L` Changes, `Esc` close overlay
- **Inline session rename** — click the titlebar session title to edit
- **Opt-in usage telemetry** — anonymous aggregate upload when enabled; off by default

### Changed

- macOS bundle identifier `sh.lori`; user data under `~/.lori/`
- Background idle PTYs auto-suspend after 1 minute; running and permission sessions stay alive

### Security

- Hook server validates requests with a shared secret (`X-Lori-Secret`)
- Provider and MCP secrets stored locally under `~/.lori/` (plaintext during beta; Keychain planned)

### Install notes

- **Platform:** macOS 10.15+ on Apple Silicon (M1/M2/M3/M4)
- **First launch:** if macOS blocks the app, right-click Lori → **Open**, or allow in **System Settings → Privacy & Security** (unsigned beta build)

[0.1.0]: https://github.com/loridotsh/lori-updates/releases/tag/v0.1.0
