# Workflow Packs

A Cursor Marketplace multi-plugin repo: design-log foundation, and full workflows for Rust, Python, JS/TS, and Terraform (design review, implementation, testing, bugfix, PR review), plus documentation and security commands.

## Structure

- **`.cursor-plugin/marketplace.json`** — Marketplace manifest (lists all plugins).
- **`design-log-foundation/`** — Design-log methodology and manual create/record-step commands.
- **`rust-workflow/`** — Full Rust workflow plus documentation and security.
- **`python-workflow/`**, **`js-ts-workflow/`**, **`terraform-workflow/`** — Full language workflows (design review, implementation, testing, bugfix, review) plus documentation and security.
- **`schemas/`** — JSON schemas for plugin and marketplace manifests.
- **`scripts/validate-plugins.mjs`** — Validates manifests and plugin structure.

## Validate

From this directory:

```bash
npm install
npm run validate
```

## Publish

1. Set `owner` in `.cursor-plugin/marketplace.json` and `author` in each plugin’s `.cursor-plugin/plugin.json`.
2. Optionally add `assets/logo.png` per plugin and set `logo` in each plugin.json.
3. Run `npm run validate`, then submit to the [Cursor Marketplace](https://cursor.com/marketplace/publish).

## Plugins

| Plugin | Description |
|--------|-------------|
| design-log-foundation | Design-log foundation and manual create/record-step commands. Pair with a language workflow for full workflow. |
| rust-workflow | Rust workflow: design review, implementation, testing, bugfix, PR review; documentation and security. |
| python-workflow | Python workflow: design review, implementation, testing, bugfix, PR review; documentation and security. |
| js-ts-workflow | JS/TS workflow: design review, implementation, testing, bugfix, PR review; documentation and security. |
| terraform-workflow | Terraform workflow: design review, implementation, testing, bugfix, PR review; documentation and security. |
