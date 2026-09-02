# Changelog

All notable changes to Cathy are documented in this file. Cathy follows
[Semantic Versioning](https://semver.org/) for published releases.

## [0.1.0-alpha.1] - Unreleased

### Added

- Interactive terminal agent with streaming responses, native file and Bash
  tools, persistent threads, model selection, and thread continuation.
- Anthropic, OpenAI, OpenAI-compatible, ChatGPT/Codex, and GitHub Copilot
  provider integrations using API-key or OAuth authentication as applicable.
- Anthropic Messages, OpenAI Chat Completions, OpenAI Responses, and Codex
  Responses protocol support.
- Optional MCP tool discovery and execution over stdio and Streamable HTTP.
- Lazy-loaded project and user skills from `.agents/skills` and
  `.claude/skills`.
- Metadata-only local JSONL telemetry and opt-in OTLP export.
- Linux, macOS, and Windows release archives for amd64 and arm64, with SHA-256
  checksums and per-archive SBOMs.

### Changed

- The module now uses `github.com/charles-chenzz/cathy`, and the user-facing
  command is built from `cmd/cathy` as `cathy`.
- Release builds expose their tag through `cathy --version`.

### Security

- Updated the Go toolchain and reachable dependencies to remove known reachable
  vulnerabilities detected before this release.
- Added vulnerability scanning to CI and the release quality gate.
- Cathy-created credential and state files use mode `0600`; native file tools
  enforce workspace boundaries, and every Bash command requires approval.

### Known limitations

- Alpha storage and configuration formats may change incompatibly.
- Approved Bash commands execute locally without an isolation sandbox.
- Credentials are stored in a local permission-restricted file rather than an
  operating-system keychain.
- macOS and Windows binaries are not yet code-signed or notarized; Windows is
  experimental pending broader real-device testing.
- There is no automatic updater.
- Cathy's ACP and MCP surfaces intentionally implement only the subsets listed
  in the project README.
