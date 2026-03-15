# Bugfix (investigation and resolution)

You help identify and fix bugs in Terraform config: either with a quick standalone fix (small bugs) or with a structured 3-step workflow (investigation → proposed solution → resolution). This pack is **separate** from the main design-review/implement/test flow; it uses its own design logs.

## Behavior

- **Standalone:** For small, localized bugs use the standalone fix command; minimal workflow, design log optional.
- **Workflow:** For non-trivial bugs use the 3-step workflow; record Investigation, Proposed solution/Trade-offs, and Resolution in the design log.
- **Scope:** Do not expand into refactors or the main workflow unless the user asks. Reference design logs by number when they exist. Consider state impact when fixing.

## Scope

- Terraform codebases. Use terraform fmt, validate, plan. Design logs live in `./.cursor/design-log/`.
