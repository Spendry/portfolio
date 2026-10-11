# AI Engineering

Empirical research, applied front-end tools, and pipeline systems that produce repeatable output.

---

## Ensemble Spread Is Not Posterior Uncertainty

A small empirical result that bridges two published papers on deep-ensemble uncertainty. On a regression task with a deliberate hole in the training data, the correct Bayesian posterior under each width's implicit prior holds flat while the ensemble spread that practitioners read as epistemic uncertainty collapses by 7.7x across a 32x range of width. The collapse belongs to the estimator, not the thing measured.

- **Repo:** https://github.com/Spendry/ensemble-spread
- **Shows:** empirical ML research, reproducible experiment design, and honest failure accounting.

## Claude Code Mods

Three mods that change what Claude Code does and shows, published as a plugin marketplace, so each one installs with a single command. deviation-kernel keeps the assumptions a project refuses in the system prompt and stops an edit that brings one back at the step where it lands; cache-meter shows how long the prompt cache stays warm and what a miss would cost; goal-board shows each session's goal, progress and ETA, with a board of every running session. Each ships with tests that run without a live session.

- **Repo:** https://github.com/Spendry/claude-code-mods
- **Shows:** Claude Code plugin development (hooks, terminal UI, slash commands), test-driven extension work, packaging tools for others to install.

## Personal Development Stack

A React application that tracks progress across multiple tracks and boosts, organised into lanes, with data that persists between sessions.

- **Repo:** In Progress
- **Shows:** front-end build skill, state management, the discipline of shipping a tool you use yourself.

## Concept Foundry Pipeline

A skill system that rolls a business concept, packages it into a founder-ready set of documents, and validates it against release criteria.

- **Repo:** In Progress
- **Shows:** pipeline design, staged validation, output you can run again and again with consistent quality.

---
