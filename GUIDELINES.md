# Coding Guidelines — four-git-mcp

## Tech Stack
- Runtime: Bun
- Language: TypeScript (`strict`)
- Module: ESM
- License: Apache-2.0

## Code Style
- One tool per file in `src/tools/`; shared logic in `src/lib/`
- `src/lib/` has no dependency on the MCP SDK
- Formatting functions are pure and exported for tests
- Tool output is compact: one line per result, no decoration
- User-supplied text is passed as arguments, never interpolated into a shell command
- No secrets in output, logs or error messages

## Build Discipline
- EVERY code change ends with: version bump + build
- No merge without current build output

## File Conventions
- LF line endings
- UTF-8 encoding
- `.local.md` files are gitignored — use for personal dev config
- No personal paths in committed code

## License Header
```
// SPDX-License-Identifier: Apache-2.0
// Copyright (c) 2026 Four Bytes
```
