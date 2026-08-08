# Frezpo

[![frezpo.com](https://img.shields.io/badge/site-frezpo.com-black)](https://frezpo.com)

Frezpo turns one client brief into a matched Google Ads and landing page strategy pack — ad architecture, landing page strategy, and design tokens — generated together so the ad's promise and the page's headline never drift apart.

This repository has no source code and never will. It exists so the project has a real, indexed page on GitHub. The product runs at **[frezpo.com](https://frezpo.com)** — this is a pointer, not a codebase. If you cloned this expecting to run something, there is nothing here to run.

## The problem it targets

Message match — whether the ad's promise survives intact to the landing page hero — is usually checked after the fact. The ad gets written by one person or agency, the landing page by another, often weeks apart, and match only gets audited once both artifacts already exist. By the time anyone notices they've drifted, the budget is already spent on clicks that bounced.

Frezpo treats message match as a production property instead of a review property. It authors the ad and the landing page from the same brief in the same run, so they agree with each other before anyone builds either one.

## How it works

A 7-node sequential LangGraph pipeline takes one input — a client brief — and produces the full pack:

1. Marketing Strategist
2. Search Intent Mapper
3. Conversion Architect
4. Hook Generator
5. Copywriter
6. UX Strategist
7. Frontend Developer

Each node reads only the distilled output of the node immediately before it — never the raw brief, never the full run history. That constraint is deliberate: it keeps token cost flat as the pipeline gets deeper and stops prompt drift from accumulating over a long agent chain, which is the usual failure mode once a sequential pipeline grows past three or four steps.

Try it without an account: [frezpo.com/stream-demo](https://frezpo.com/stream-demo/).

## Published agent skills

Frezpo publishes three of its internal skills as machine-readable `SKILL.md` files, each listed with a sha256 in a discovery index any agent can fetch and verify before using:

- **message-match-audit** — diagnoses whether a landing page delivers on the promise its ad made
- **ad-to-hero-alignment** — writes a hero so it aligns with the specific ad hook that sent the visitor there
- **campaign-pack-handoff** — hands an approved strategy pack to whoever builds it next, human or LLM

Index: [frezpo.com/.well-known/agent-skills/index.json](https://frezpo.com/.well-known/agent-skills/index.json). Human-facing hub: [frezpo.com/skills](https://frezpo.com/skills/). Also see [llms.txt](https://frezpo.com/llms.txt).

## Built by

[Özer Yılmaztekin](https://github.com/oyilmaztekin/), Principal Engineer, 15+ years, İzmir, Türkiye. Built and maintained solo.

## Links

- Site: https://frezpo.com
- About: https://frezpo.com/about/
- Blog: https://frezpo.com/blog/
- Pricing: https://frezpo.com/pricing/
- Interactive demo: https://frezpo.com/stream-demo/
- Agent skills hub: https://frezpo.com/skills/
- Skills index (machine-readable): https://frezpo.com/.well-known/agent-skills/index.json
- llms.txt: https://frezpo.com/llms.txt
- LinkedIn: https://www.linkedin.com/company/frezpo-ai/
- X: https://x.com/frezpoai
- Contact: https://frezpo.com/contact/
