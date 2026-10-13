# Security Policy

## Supported Versions

Until 1.0, only the latest released version receives security fixes.

## Reporting a Vulnerability

Please do **not** open a public issue for security problems.

Use GitHub's private vulnerability reporting:
**Security → Report a vulnerability** in this repository
(<https://github.com/four-bytes/four-git-mcp/security/advisories/new>).

Include the affected version, a description of the problem and, where possible, steps to
reproduce. You can expect a first response within 7 days.

## Scope

This server runs `git` and calls forge APIs with tokens from the local machine. Reports of
particular interest:

- command or argument injection through tool arguments
- token disclosure in tool output, logs or error messages
- tools acting on a repository or directory other than the resolved one
