# AGENTS.md

Guidance for AI coding agents working with this repository.

## What is four-git-mcp?

An MCP server (stdio) that exposes git analysis and Forgejo / GitHub / GitLab operations as
tools. It replaces the tool part of the opencode plugin `four-opencode-git` so that every MCP
client uses the same tools. Status: skeleton only — the extraction is tracked in issue #1.

## Build & Development Commands

Planned — the scripts arrive with the first code (issue #1).

| Command | Description |
|---------|-------------|
| `bun install` | Install dependencies |
| `bun run build` | Build the server to `dist/` |
| `bun test` | Run the test suite |
| `bun run lint` | Typecheck (`tsc --noEmit`) |

## Architecture (target)

- **`src/lib/`** — host and git logic (Forgejo, GitHub, GitLab, git utils, secrets); no MCP imports
- **`src/tools/`** — one file per tool: name, description, schema, handler taking `{ args, cwd }`
- **`src/server.ts`** — stdio entry point; registers the tools with the MCP SDK
- **`src/lib/cwd.ts`** — working-directory resolution: `cwd` argument → MCP root → process cwd
- **`tests/`** — `bun test`

## Key Conventions

- TypeScript, ESM, **Bun** (never Node.js); `strict` enabled
- Every tool takes an optional `cwd`; every result starts with repository and branch
- Tool arguments carry all text — nothing is passed through a shell
- Output: compact, one line per result
- Write tools refuse to act on the default branch where that would bypass a pull request
- LF line endings, UTF-8; license header on every source file (see GUIDELINES.md)
- Conventional commits with issue reference: `feat: description (#42)`
- Branch naming: `feat/{nr}-desc`, `fix/{nr}-desc`
- Issue first; never commit to `main`; version bump + HISTORY.md entry with every change

## Tech Stack

TypeScript, Bun, `@modelcontextprotocol/sdk`

## Dependencies

- **Depends on:** `git` CLI; `gh` CLI for the GitHub tools; Forgejo and GitLab REST APIs (token per host)
- **Used by:** MCP clients — opencode, Claude Code

Local, machine-specific notes belong in `AGENTS.local.md` (gitignored).
