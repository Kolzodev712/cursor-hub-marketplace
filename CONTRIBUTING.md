# Contributing to Workflow Packs

Thanks for your interest in contributing to Workflow Packs. This document explains how to get set up, validate changes, and submit contributions.

## Prerequisites

- Node.js (for running the validation script)
- A Cursor-compatible environment if you want to test plugins locally

## Development setup

1. **Clone the repo** (or your fork):
   ```bash
   git clone <repo-url>
   cd cursor-hub-marketplace
   ```

2. **Install dependencies and validate**:
   ```bash
   npm install
   npm run validate
   ```
   All contributions must pass `npm run validate` before submission.

## Project structure

- **`.cursor-plugin/marketplace.json`** — Marketplace manifest; lists all plugins. Update this when adding or renaming plugins.
- **`design-log-foundation/`** — Design-log methodology and manual create/record-step commands.
- **`rust-workflow/`**, **`python-workflow/`**, **`js-ts-workflow/`**, **`terraform-workflow/`** — Language-specific workflows (design review, implementation, testing, bugfix, PR review) plus documentation and security.
- **`schemas/`** — JSON schemas for plugin and marketplace manifests.
- **`scripts/validate-plugins.mjs`** — Validates manifests and plugin structure.

Each plugin has:
- **`.cursor-plugin/plugin.json`** — Plugin manifest (name, description, author, commands, agents, rules).
- **`commands/`** — Command definitions (`.md`).
- **`agents/`** — Agent definitions (`.md`).
- **`rules/`** — Rule files (`.mdc`).

## How to contribute

### Reporting issues

- Open an issue describing the bug, missing feature, or unclear docs.
- For bugs, include steps to reproduce and your environment (OS, Node version, Cursor version if relevant).

### Submitting changes

1. **Fork** the repository and create a branch from `main`:
   ```bash
   git checkout -b fix/short-description
   # or
   git checkout -b feature/short-description
   ```

2. **Make your changes** and keep them focused (one logical change per PR when possible).

3. **Validate** before committing:
   ```bash
   npm run validate
   ```

4. **Commit** with a clear message, e.g.:
   - `fix(js-ts-workflow): correct reviewer prompt`
   - `feat(design-log): add command for decision summary`
   - `docs: update CONTRIBUTING setup steps`

5. **Push** to your fork and open a **Pull Request** against `main`.
   - Describe what changed and why.
   - Ensure CI (if any) and `npm run validate` pass.

### Adding a new plugin

1. Create a new directory (e.g. `go-workflow/`) with the same structure as existing workflows: `.cursor-plugin/plugin.json`, `commands/`, `agents/`, `rules/` as needed.
2. Add an entry to the `plugins` array in `.cursor-plugin/marketplace.json` with `name`, `source`, and `description`.
3. Run `npm run validate` and fix any schema or structural errors.
4. Open a PR with a short description of the new workflow and its commands/agents.

### Code and content standards

- **Manifests**: Follow the JSON schemas in `schemas/`. The validator enforces these.
- **Markdown**: Use clear headings and consistent formatting in commands and agents.
- **Naming**: Use kebab-case for plugin folders and command/agent file names; keep IDs and references consistent with the manifest.

## Questions

If something is unclear, open an issue with the question so we can improve the docs or help directly.

Thank you for contributing.
