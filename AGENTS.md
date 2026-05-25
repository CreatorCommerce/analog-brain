# Analog Brain Instructions

## Purpose

This repo is the internal Mintlify brain for practical Analog usage: strategy, market tests, product primitives, rubrics, and how-to playbooks for running real-world activations through the Analog product.

## Source Order

Use this order when facts conflict:

1. The user in this repo. New use cases, feedback, and corrections are law of the land.
2. Current Analog product logic and frontend behavior from `analog-discovery`.
3. Market, strategy, and operator doctrine from `playground-agentic-mvp`.
4. Existing pages in this repo.

When the user gives a new use case or correction, update the page it belongs to and any conflicting downstream summaries in the same pass.

## Documentation Contract

- Every live page needs `title`, `description`, and `pageType` frontmatter.
- References own stable facts.
- Strategy pages frame market doctrine and decisions.
- How-to pages explain practical execution steps.
- Use-case pages route operators to the right pages without duplicating full reference blocks.
- Do not publish placeholders, draft stubs, or "coming soon" pages in live navigation.
- Keep docs practical and operator-grade. Avoid investor-only abstraction unless it changes how a pilot is run.

## Terminology

- Use `Sponsor` for the product actor that funds campaigns.
- Use `Host` for the product actor that creates events and uses sponsor budgets.
- Use `brand`, `tech company`, `fund`, or `public/non-profit sponsor` when describing real-world sponsor categories.
- Use `collab` for a sponsor-host relationship inside one campaign.
- Use `spend card` for a temporary operational Stripe Issuing card.
- Use `Agent MCP` for Model Context Protocol tools.
- Use `MCP attribution rail` for Measurement, Commerce, and Proof.

## Mintlify Notes

- Configuration lives in `docs.json`.
- Custom styles live in `style.css`.
- Run `mint broken-links` when available after navigation changes.
- If the Mintlify CLI is not available, validate `docs.json` as JSON and verify navigation paths manually.
