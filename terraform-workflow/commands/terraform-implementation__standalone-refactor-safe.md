# Refactor safe (Standalone)

Plan 3–6 steps; limit files per step; run validate/plan after each step; stop and show a short summary between steps.

## Steps

1. **Scope:** Identify the refactor goal and the set of files/modules affected. List them. Consider state impact (e.g. moved blocks).
2. **Plan steps:** Define 3–6 steps so that after each step `terraform validate` passes and plan is reviewed. Prefer additive steps (new resources, then update references, then remove old) over big-bang edits.
3. **Execute step by step:**
   - For each step: edit only the files needed for that step.
   - Run `terraform fmt -recursive`, `terraform validate`; optionally `terraform plan` after the step.
   - If validation fails, fix before continuing.
   - Optionally show a one-line summary of what changed in that step.
4. **Final check:** Run full verification (fmt, validate, plan). Summarize the refactor outcome.

Do not change behavior or state semantics unintentionally; refactor only structure, naming, or duplication. If state migrations are required (e.g. moved blocks), document them clearly.
