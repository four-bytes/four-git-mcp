# four-git-mcp — ROADMAP

**Owner:** Four Bytes | **Last Updated:** 2026-10-13
**Status:** Active | **Review Cycle:** Monthly

---

## Vision

One MCP server that gives every coding agent the same compact git and forge tools —
independent of the client it runs in.

---

## Phase 1: Extraction (#1)

### Server
- [ ] Tool definitions independent of the opencode plugin API
- [ ] stdio entry point, `bin`, build
- [ ] Working-directory resolution (`cwd` argument → MCP root → process cwd)
- [ ] Results name repository and branch

### Tools
- [ ] Git: status, diff, structured log, analysis
- [ ] Forgejo, GitHub, GitLab tools moved with their tests

### Release
- [ ] Client configuration documented for opencode and Claude Code
- [ ] First release

---

## Phase 2: Switch-over

- [ ] Both clients run on the server
- [ ] Tool registration removed from `four-opencode-git`

---

## Phase 3: Client extras (outside this repo)

- [ ] opencode TUI: branch / PR status in the sidebar
- [ ] Hooks, e.g. refuse commits on the default branch

---

## Metrics & Review

| Metric | Current | Target |
|--------|---------|--------|
| Tools served over MCP | 0 | all tools of `four-opencode-git` |
| Clients on the server | 0 | 2 |

---

## Decision Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-10-13 | Own repository, public, Apache-2.0 | The server is not opencode-specific |
| 2026-10-13 | One server for all hosts | One configuration, one codebase; split only if tool-definition size becomes a problem |
| 2026-10-13 | Plugin tools are removed once the server runs in both clients | No duplicate tools under different names |
| 2026-10-13 | Explicit `cwd` argument on every tool | The MCP root is static and does not follow `cd` or worktrees |
