<p align="center">
  <a href="https://opencode.ai">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode logo">
    </picture>
  </a>
</p>
<p align="center">The open source AI coding agent.</p>

> [!NOTE]
> **Independent fork notice:** This repository is an independently maintained fork of [OpenCode](https://github.com/anomalyco/opencode), maintained by [AndieKobbieTech™](https://github.com/andiekobbietks) as part of the wider Andrea Kwabena Technologies engineering ecosystem. It is not an official OpenCode project, is not produced by Anomaly, and is not endorsed by or affiliated with the upstream OpenCode team. OpenCode and related upstream marks belong to their respective owners. This fork does not claim ownership of the upstream project, its name, logo, code, or trademarks.

## Why this fork exists

This fork provides a controlled development and integration surface for exploring how an extensible coding agent can support the wider AndieKobbieTech™ ecosystem. The aim is not to recreate or claim the upstream OpenCode product. It is to maintain a usable upstream-derived foundation, evaluate integrations, and develop agent-assisted engineering workflows while keeping project-specific tools modular and independently governed.

The direction behind this work is to use OpenCode as an **operational interface for agentic engineering**: a place where a developer can work with code, invoke tools, inspect project context, and connect specialised workflows. The fork makes those integrations testable and controllable without making every ecosystem project a permanent modification to OpenCode itself.

## The wider engineering ecosystem

The names below identify separate projects, tools, or initiatives. They are not all components of this repository, and their inclusion here does not imply that they are bundled with OpenCode.

| Project / identity | What it is for | Relationship to this fork |
|---|---|---|
| **Andrea Kwabena Technologies** | The wider technology consultancy and engineering umbrella. | Parent business context for the work. |
| **AndieKobbieTech™** | The public-facing technical identity and shorthand for Andrea Kwabena Technologies. | Maintainer identity for this independent fork. |
| **OpenCode** | The upstream open-source coding-agent foundation. | The project this repository forks; upstream ownership and direction remain with its maintainers. |
| **AKT™** | A sovereign-minded cloud and infrastructure operations initiative, focused on deployable services, infrastructure management, and practical operations for smaller organisations. | A potential environment for agent-assisted infrastructure workflows; integrations should use explicit permissions and policy controls. |
| **ASAL™** | Andie's software assurance and security tooling direction, including scanner/CLI capabilities and agent-facing integration. | Intended to provide assurance checks and structured feedback within development workflows, without treating an AI agent's output as proof of security. |
| **AgentSON™** | A structured agent-event and observability initiative, using typed, machine-readable event records to make agent activity easier to inspect and audit. | A potential event/provenance layer around agent workflows; it is not an OpenCode replacement. |
| **ManusArchive** | A project to organise and retrieve exported Manus task history, execution records, and related artefacts. | A potential source of project context and historical knowledge for an agent, subject to access controls and data minimisation. |
| **Mind the Gap™** | A privacy-first recruitment and opportunity-mapping concept, including structured matching and evidence-led workflows. | A separate product initiative; not part of this fork. |
| **ClinicDx** | A separate research and product codebase exploring structured, evidence-led decision workflows. | A source of architectural learning, not an OpenCode component. |

### Design principles

- **Keep the upstream relationship clear.** Preserve attribution and upstream licensing; do not imply that this fork is the official OpenCode distribution.
- **Prefer modular integrations.** Keep specialised tools and services outside the core agent where practical, connecting them through documented interfaces, plugins, CLI tools, or other explicit integration points.
- **Make agent actions inspectable.** Prefer traceable tool calls, structured events, logs, and reviewable changes over opaque automation.
- **Apply least privilege.** Infrastructure, repositories, credentials, and external services should only be accessible through narrowly scoped permissions and deliberate approval boundaries.
- **Separate advice from execution.** Planning and analysis should be distinguishable from actions that modify code, infrastructure, or external systems.
- **Keep humans accountable for consequential changes.** Tests, security checks, code review, and deployment approval remain important; an AI agent does not replace them.
- **Treat this as an evolving integration surface.** Not every proposed integration is implemented, production-ready, or enabled by default.

### Trademark and project-name note

The ™ symbol is used here to identify project and brand names associated with this ecosystem; it does **not** by itself mean that a name is registered as a trademark. No claim of registration is made by this README. Third-party names and marks, including OpenCode, remain the property of their respective owners. Project names in this table describe intended scope and direction, not a claim that every project is shipped in this repository.

<p align="center">
  <a href="https://opencode.ai/discord"><img alt="Discord" src="https://img.shields.io/discord/1391832426048651334?style=flat-square&label=discord" /></a>
  <a href="https://www.npmjs.com/package/@opencode/cli"><img alt="npm" src="https://img.shields.io/npm/v/@opencode/cli?style=flat-square" /></a>
  <a href="https://github.com/anomalyco/opencode/actions/workflows/publish.yml"><img alt="Build status" src="https://img.shields.io/github/actions/workflow/status/anomalyco/opencode/publish.yml?style=flat-square&branch=dev" /></a>
</p>

<p align="center">
  <a href="README.md">English</a> |
  <a href="README.zh.md">简体中文</a> |
  <a href="README.zht.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <a href="README.de.md">Deutsch</a> |
  <a href="README.es.md">Español</a> |
  <a href="README.fr.md">Français</a> |
  <a href="README.it.md">Italiano</a> |
  <a href="README.da.md">Dansk</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.pl.md">Polski</a> |
  <a href="README.ru.md">Русский</a> |
  <a href="README.bs.md">Bosanski</a> |
  <a href="README.ar.md">العربية</a> |
  <a href="README.no.md">Norsk</a> |
  <a href="README.br.md">Português (Brasil)</a> |
  <a href="README.th.md">ไทย</a> |
  <a href="README.tr.md">Türkçe</a> |
  <a href="README.uk.md">Українська</a> |
  <a href="README.bn.md">বাংলা</a> |
  <a href="README.gr.md">Ελληνικά</a> |
  <a href="README.vi.md">Tiếng Việt</a>
</p>

[![OpenCode Terminal UI](packages/web/src/assets/lander/screenshot.png)](https://opencode.ai)

---

### Installation

```bash
# YOLO
curl -fsSL https://opencode.ai/v2/install | bash

# Package managers
npm i -g @opencode/cli@latest      # or bun/pnpm/yarn
brew install anomalyco/tap/opencode-v2 # macOS and Linux (recommended, always up to date)
brew install opencode              # macOS and Linux (official brew formula, updated less)
sudo pacman -S opencode            # Arch Linux (Stable)
paru -S opencode-beta              # Arch Linux (Latest from AUR)
mise use -g opencode               # Any OS
nix run github:anomalyco/opencode  # Nix
```

> [!TIP]
> Remove versions older than 0.1.x before installing.

### Desktop App (BETA)

OpenCode is also available as a desktop application. Download it from [opencode.ai/download](https://opencode.ai/download).

| Platform              | Download                           |
| --------------------- | ---------------------------------- |
| macOS (Apple Silicon) | `opencode-desktop-mac-arm64.dmg`   |
| macOS (Intel)         | `opencode-desktop-mac-x64.dmg`     |
| Windows               | `opencode-desktop-win-x64.exe`     |
| Linux                 | `.deb`, `.rpm`, or `.AppImage`     |

```bash
# macOS (Homebrew)
brew install --cask opencode-desktop
```

#### Installation Directory

The install script respects the following priority order for the installation path:

1. `$OPENCODE_INSTALL_DIR` - Custom installation directory
2. `$XDG_BIN_DIR` - XDG Base Directory Specification compliant path
3. `$HOME/bin` - Standard user binary directory (if it exists or can be created)
4. `$HOME/.opencode/bin` - Default fallback

```bash
# Examples
OPENCODE_INSTALL_DIR=/usr/local/bin curl -fsSL https://opencode.ai/v2/install | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://opencode.ai/v2/install | bash
```

### Agents

OpenCode includes two built-in agents you can switch between with the `Tab` key.

- **build** - Default, full-access agent for development work
- **plan** - Read-only agent for analysis and code exploration
  - Denies file edits by default
  - Asks permission before running bash commands
  - Ideal for exploring unfamiliar codebases or planning changes

Also included is a **general** subagent for complex searches and multistep tasks.
This is used internally and can be invoked using `@general` in messages.

Learn more about [agents](https://opencode.ai/docs/agents).

### Documentation

For more info on how to configure OpenCode, [**head over to our docs**](https://opencode.ai/docs).

### Contributing

If you're interested in contributing to OpenCode, please read our [contributing docs](./CONTRIBUTING.md) before submitting a pull request.

### Building on OpenCode

If you are working on a project that's related to OpenCode and is using "opencode" as part of its name, for example "opencode-dashboard" or "opencode-mobile", please add a note to your README to clarify that it is not built by the OpenCode team and is not affiliated with us in any way.

---

**Join our community** [Discord](https://discord.gg/opencode) | [X.com](https://x.com/opencode)
