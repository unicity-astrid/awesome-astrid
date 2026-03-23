# Awesome Astrid [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome projects, tools, capsules, and resources for [Astrid OS](https://github.com/unicity-astrid/astrid) — an operating system for AI agents.

Astrid is a user-space microkernel that treats AI agents the way Linux treats processes. Everything above the kernel boundary is a swappable **capsule**: providers, orchestrators, tools, frontends, interceptors.

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

---

## Contents

- [Official Resources](#official-resources)
- [Core Capsules](#core-capsules)
  - [LLM Providers](#llm-providers)
  - [Orchestrators](#orchestrators)
  - [Tools](#tools)
  - [Memory & Context](#memory--context)
  - [Identity & Auth](#identity--auth)
  - [Frontends & Uplinks](#frontends--uplinks)
  - [Infrastructure](#infrastructure)
- [Community Capsules](#community-capsules)
- [SDKs & Libraries](#sdks--libraries)
- [Distros & Configurations](#distros--configurations)
- [Tools & Utilities](#tools--utilities)
- [Documentation & Tutorials](#documentation--tutorials)
- [Community](#community)

---

## Official Resources

- [astrid](https://github.com/unicity-astrid/astrid) - The Astrid OS kernel and runtime. Microkernel, VFS, IPC bus, WASM sandbox, security interceptor, audit log.
- [sdk-rust](https://github.com/unicity-astrid/sdk-rust) - Official Rust SDK for building Astrid capsules. Includes the `#[capsule]` proc macro and the full host ABI syscall table.
- [wit](https://github.com/unicity-astrid/wit) - Canonical WIT interface definitions for Astrid OS. Typed contracts between capsules.
- [rfcs](https://github.com/unicity-astrid/rfcs) - RFCs for the Astrid agent runtime. Design proposals and accepted specifications.
- [astralis](https://github.com/unicity-astrid/astralis) - The flagship Astrid distribution. Curated capsule bundle for the complete AI assistant experience.

## Core Capsules

Official capsules maintained by the Astrid team.

### LLM Providers

- [capsule-openai-compat](https://github.com/unicity-astrid/capsule-openai-compat) - OpenAI-compatible LLM provider. Real-time SSE streaming via the Chat Completions API. Works with Anthropic, OpenAI, Ollama, vLLM, and any compatible endpoint.

### Orchestrators

- [capsule-react](https://github.com/unicity-astrid/capsule-react) - ReAct loop coordinator. Stateless state machine for the reasoning-and-action cycle.

### Tools

- [capsule-fs](https://github.com/unicity-astrid/capsule-fs) - Filesystem tools for agents. Read, write, replace, grep, list, create, delete, move via the VFS airlock.
- [capsule-shell](https://github.com/unicity-astrid/capsule-shell) - Shell execution tools. Subcommand-aware approval, catastrophic command blocking, background processes.
- [capsule-http](https://github.com/unicity-astrid/capsule-http) - HTTP fetch tool. URL validation, method allowlist, SSRF protection, response truncation.
- [capsule-system](https://github.com/unicity-astrid/capsule-system) - System management tools. Lets the agent inspect and manage its own Astrid OS runtime.
- [capsule-skills](https://github.com/unicity-astrid/capsule-skills) - Skills loader. Discovers `SKILL.md` files from workspace and global directories with path traversal protection.
- [capsule-agents](https://github.com/unicity-astrid/capsule-agents) - Injects project instructions from `AGENTS.md` into the Astrid system prompt.

### Memory & Context

- [capsule-memory](https://github.com/unicity-astrid/capsule-memory) - Cross-session memory. Reads `.astrid/memory.md` and injects it into the system prompt via hook.
- [capsule-context-engine](https://github.com/unicity-astrid/capsule-context-engine) - Context window compaction. Token-budget trimming with interceptor hooks for pinning and skip.
- [capsule-session](https://github.com/unicity-astrid/capsule-session) - Conversation session store. Append-only history with schema versioning and session chaining.

### Identity & Auth

- [capsule-identity](https://github.com/unicity-astrid/capsule-identity) - System prompt builder. Assembles agent identity from workspace config and `spark.toml`.

### Frontends & Uplinks

- [capsule-cli](https://github.com/unicity-astrid/capsule-cli) - CLI proxy. Unix socket bridge between the TUI frontend and the kernel IPC bus. Multi-client, topic-filtered.

### Infrastructure

- [capsule-prompt-builder](https://github.com/unicity-astrid/capsule-prompt-builder) - Prompt assembly pipeline. Hook-based plugin contributions with permission-gated merging.
- [capsule-router](https://github.com/unicity-astrid/capsule-router) - Tool execution router. Validates and forwards tool requests to the correct capsule topic.
- [capsule-hook-bridge](https://github.com/unicity-astrid/capsule-hook-bridge) - Lifecycle-to-hook mapper. Fans out kernel events to subscribers with typed merge strategies.
- [capsule-registry](https://github.com/unicity-astrid/capsule-registry) - LLM provider registry. Discovers providers from manifests and manages model selection.

## Community Capsules

> Community-built capsules extending Astrid with new tools, providers, and orchestrators.
>
> *Be the first to add your capsule! See [CONTRIBUTING.md](CONTRIBUTING.md).*

## SDKs & Libraries

- [sdk-rust](https://github.com/unicity-astrid/sdk-rust) - Official Rust SDK. The `astrid-sdk` crate with typed ergonomics mirroring `std` module layout: `fs`, `net`, `process`, `env`, `time`, `log`, plus Astrid-specific modules: `ipc`, `kv`, `http`, `hooks`, `cron`, `uplink`, `identity`, `approval`, `runtime`.

## Distros & Configurations

> `config.toml` + capsule bundles targeting specific use cases or deployment environments.

- [astralis](https://github.com/unicity-astrid/astralis) - The flagship distribution. Curated capsule bundle for the complete AI assistant experience.

## Tools & Utilities

> Build tools, CLIs, and developer utilities for working with Astrid capsules.

- [astrid-build](https://github.com/unicity-astrid/astrid) - Capsule compiler and packager (`astrid-build` binary). Handles Rust, OpenClaw (JS/TS via OXC + QuickJS/Wizer), and legacy MCP projects.

## Documentation & Tutorials

- [Astrid OS README](https://github.com/unicity-astrid/astrid#readme) - Comprehensive overview: architecture, security model, host ABI, quick start, and capsule authoring guide.
- [RFCs](https://github.com/unicity-astrid/rfcs) - Design proposals and accepted specifications for the Astrid runtime.
- [WIT Interfaces](https://github.com/unicity-astrid/wit) - Typed interface contracts between capsules.

## Community

- [GitHub Discussions](https://github.com/unicity-astrid/astrid/discussions) - Questions, ideas, and community conversation.
- [Issues](https://github.com/unicity-astrid/astrid/issues) - Bug reports and feature requests for the Astrid kernel.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add your project, fix a broken link, or suggest a new category.
