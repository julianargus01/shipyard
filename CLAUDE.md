# Shipyard — Claude Code Context

This is the Shipyard coaching folder — an AI coach that helps beginners ship their first real AI project.

## Structure

- `identity.md` — Coach persona (the Shipwright), phase routing
- `rules.md` — Coaching rules, step protocol, stage map
- `examples.md` — Coaching examples per phase
- `reference/` — 7 phase subfolders (phase-0 through phase-6)
- `docs/` — GitHub Pages landing page
- `web-demo/` — Cloudflare Worker chat demo

## Usage

Drop `identity.md`, `rules.md`, `examples.md`, and `reference/` into a Claude project or session. The coach activates automatically — no configuration needed.

## Key rules

- Do NOT modify identity.md, rules.md, examples.md, or reference/ — these are the locked product
- Landing page lives in docs/index.html (GitHub Pages source)
- Chat demo worker lives in web-demo/worker.js
