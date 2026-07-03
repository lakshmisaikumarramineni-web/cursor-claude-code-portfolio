# Cursor + Claude Code Setup — Portfolio Project

This repo documents my process setting up Cursor IDE with the Claude Code and
Codex AI coding assistants, as part of the 100Hires application process. It's
a real account of what I installed, what broke, and how I fixed it — not a
polished retelling.

## Tools installed

- **Cursor IDE** — the code editor itself
- **Node.js** (LTS) — required as a dependency for installing Claude Code via npm
- **Claude Code CLI** (v2.1.199) — Anthropic's terminal-based AI coding agent
- **Codex** — *(in progress — see Next Steps)*

## Steps completed

1. Installed Cursor IDE from cursor.com and signed in
2. Tried installing the Claude Code extension through Cursor's Extensions
   panel — hit a dead end (see Issues below) and pivoted to installing the
   Claude Code CLI directly via the terminal instead
3. Installed Node.js (LTS) after discovering it wasn't already on my machine
4. Fixed a PowerShell execution policy restriction blocking npm scripts
5. Installed Claude Code globally via npm
6. Authenticated Claude Code using an Anthropic Console account (API billing),
   since I don't have a paid Claude subscription
7. Successfully logged in and reached the Claude Code interactive prompt

## Issues I ran into (and how I solved them)

**1. Couldn't find the Claude Code extension in Cursor's Extensions panel**
Cursor's newer UI doesn't expose a classic "Extensions: Install Extensions"
command the way older tutorials describe. I tried the direct install link
(`cursor:extension/anthropic.claude-code`), which threw a
`Cannot read properties of undefined (reading 'activeEditor')` error. Rather
than keep chasing the GUI extension, I switched strategy and installed the
**Claude Code CLI** directly through the terminal — which turned out to be
the more standard way to use it anyway.

**2. Install script failed with a TLS/connection error**
The official install command (`curl -fsSL ... | bash`) doesn't work on
Windows PowerShell — `bash` isn't a recognized command there. I switched to
the PowerShell-specific installer (`irm ... | iex`), which then failed with
`The connection was closed unexpectedly`. I forced TLS 1.2 for the session,
which didn't resolve it either — so I abandoned the install script entirely.

**3. Node.js wasn't installed**
Diagnosing the above, I found neither `node` nor `npm` were recognized
commands on my machine. Installed Node.js LTS from nodejs.org, restarted
Cursor so the terminal would pick up the new PATH, and confirmed with
`node --version` / `npm --version`.

**4. PowerShell blocked npm from running scripts**
Once Node was installed, `npm --version` failed with a `PSSecurityException`
— running scripts was disabled by Windows' default execution policy. Fixed
with:
```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```
This allows locally created and signed scripts to run, without disabling the
protection against arbitrary unsigned scripts from the internet.

**5. Login flow stalled mid-authentication**
The OAuth login redirect (through Google sign-in) got stuck on an
intermediate `accounts.google.com/gsi/transform` page. I cancelled
(`Ctrl+C`) and restarted the login flow (`claude`) fresh, which completed
successfully on retry.

**6. Transient DNS failure**
One login attempt failed with `Failed to connect to api.anthropic.com:
ENOTFOUND`. Retrying the same command a minute later worked without any
network changes — likely a momentary DNS blip rather than a real
connectivity issue.

**7. Free API credits ran out before I could run a live test**
After successfully authenticating, my Anthropic Console free credits had
already been used, so I couldn't run a live prompt inside Claude Code. I
verified the CLI, install, and authentication all worked correctly up to
that point via the "Welcome back!" screen and account details Claude Code
displayed. Adding a small amount of credit (~$5, pay-as-you-go, no
subscription) would resolve this if a live test is needed.

## What I learned

Most of the real difficulty here had nothing to do with AI tools
specifically — it was standard developer environment setup: PATH issues,
Windows execution policies, OAuth redirects, and DNS flakiness. None of it
was unsolvable, but it required reading actual error messages carefully
rather than assuming the first fix would work, and being willing to abandon
one approach (the GUI extension) for a more reliable one (the CLI) when it
wasn't panning out.

## Next steps

- Install and authenticate the Codex extension/CLI
- (Optional) Add API credit to run a live Claude Code test session
