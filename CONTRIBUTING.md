# Contributing to four-git-mcp

## Golden Workflow

1. **Issue first** — Every change starts with a GitHub issue (purpose, scope, acceptance criteria).
2. **Branch** — `feat/{issue}-description`, `fix/{issue}-description`, etc. Never commit to `main`.
3. **Code** — Follow [GUIDELINES.md](GUIDELINES.md). Version bump after every change.
4. **Test** — `bun run lint` and `bun test` must pass.
5. **PR** — Open a pull request with description and checklist. Link the issue.
6. **Review** — All PRs require review. Merge only when passing.
7. **Cleanup** — Squash-merge, delete the branch after merge.

## Commit Convention

[Conventional Commits](https://www.conventionalcommits.org/):
```
feat: description (#issue)
fix: description (#issue)
chore: description (#issue)
docs: description (#issue)
refactor: description (#issue)
```

## Branch Naming

```
feat/{nr}-short-description
fix/{nr}-short-description
chore/{nr}-short-description
docs/{nr}-short-description
```

## Build & Test

```bash
bun install
bun run build
bun run lint
bun test
```

## PR Checklist

- [ ] Conventional commit format
- [ ] Tests pass
- [ ] Build succeeds
- [ ] Version bumped
- [ ] No personal paths in committed files
- [ ] HISTORY.md updated for user-facing changes

## Conduct and Security

Participation is covered by the [Code of Conduct](CODE_OF_CONDUCT.md).
Report vulnerabilities as described in [SECURITY.md](SECURITY.md), not in public issues.

## License

By contributing, you agree that your contributions will be licensed under Apache-2.0.
