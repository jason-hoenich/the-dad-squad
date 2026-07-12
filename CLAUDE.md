# The Dad Squad - Claude Context & Guidelines

## Delegation Policy (token efficiency)

Agent definitions in .claude/agents/: recon (haiku, read-only sweeps), code-mechanic (sonnet, specced code changes), verifier (haiku, post-change checks). The orchestrating model handles diagnosis, decisions, prod data, and credentials, and delegates by default:

- Codebase sweeps, find-usages, audits: spawn recon, act on its report
- Mechanical or batch code changes with a clear spec: spawn code-mechanic with the spec
- Post-change verification (tsc, endpoint probes, assertions): spawn verifier
- Do the work inline only when it is small (under ~3 files), judgment-heavy, or touches production data

## Working Preferences

- Never use em dashes in any written content
- Never use standard LLM template writing ("it's not x, it's y" constructions, "let me be clear," "here's the thing")
- Never work in a sandbox. Use real tools, real MCPs, real browser sessions.
- Do the work via tools and browser. Don't ask Jason to do things manually unless they require his credentials.
- Keep responses concise. No corporate fluff.

## Strategic Context

Read these files from `/context/` for full operational awareness. These are the source of truth.

- `context/product.md` -- what DadSquad is, service areas, positioning
- `context/decisions.md` -- dated log of strategic decisions (append-only, newest at top)

When a strategic decision is made during a session, append it to `context/decisions.md` immediately with the date.

---

# Project Details

## What This Is

Single-page static site for The Dad Squad, a rent-a-dad handyman service. Deployed on Vercel.

## Stack

- Single HTML file (index.html) with inline CSS and JS
- Static images (JPG/JPEG)
- Hosted on Vercel via vercel.json config
- No build step, no framework

## Deployment

- Hosting: Vercel (auto-deploys from main)
- Repo: the-dad-squad on GitHub
