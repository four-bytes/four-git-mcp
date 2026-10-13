# four-git-mcp

MCP server with git analysis and Forgejo / GitHub / GitLab tools for coding agents.

One server, one set of tools — usable from any MCP client (opencode, Claude Code, …).

> **Status: planning.** The repository holds the project skeleton. The tools are being
> extracted from [four-opencode-git](https://github.com/four-bytes/four-opencode-git);
> see [issue #1](https://github.com/four-bytes/four-git-mcp/issues/1) and [ROADMAP.md](ROADMAP.md).

## What it will provide

- **Git** — compact status, diff and structured log; repository analysis (file risk, ownership,
  coupling, PR risk)
- **Forgejo** — issues, comments, pull requests, merge
- **GitHub** — issues, pull requests, reviews, releases
- **GitLab** — issues, merge requests

Output is compact, one line per result, built to keep an agent's context small.

## Working directory

Tools resolve the repository in this order:

1. the `cwd` argument of the call
2. the MCP root reported by the client
3. the directory the server was started in

Pass `cwd` whenever the agent works outside the project root (git worktree, second repository).
Every result names the repository and branch it acted on.

## Install and configure

Not released yet. Client configuration for opencode and Claude Code follows with the first release.

## Documentation

- [ROADMAP.md](ROADMAP.md) — phases and decisions
- [HISTORY.md](HISTORY.md) — changelog
- [CONTRIBUTING.md](CONTRIBUTING.md) — workflow for changes
- [GUIDELINES.md](GUIDELINES.md) — coding standards
- [AGENTS.md](AGENTS.md) — conventions for AI coding agents
- [SECURITY.md](SECURITY.md) — reporting vulnerabilities
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

## License

[Apache-2.0](LICENSE) — Copyright (c) 2026 Four Bytes
