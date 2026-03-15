# Implement module (terraform-implementation WF Step 1)

Implement from an approved design log when one exists. Cite the log; make stepwise edits; run the verification loop after each logical step. You can use this command on its own (e.g. after a design done elsewhere) — no requirement to run any other pack's workflow first.

## Steps

1. **Identify the design log:** Note which design log or log number is being implemented. If the user did not specify, ask or infer from context. If there is no log yet, you will create one when recording (step 6).
2. **Plan phases:** Break the implementation into 3–6 small phases (e.g. "add variables", "add resources", "add outputs"). Do not implement everything in one large edit.
3. **Per phase:**
   - Make only the edits for that phase. Limit files changed per step where possible.
   - Run verification: `terraform fmt -recursive`, `terraform validate`; optionally `terraform plan`. Fix any failures.
   - Optionally summarize what changed before moving to the next phase.
4. **Deviations:** If implementation diverged from the design, document why in the log.
5. **Record in design log (mandatory):** Append the design log with an **Implementation Results** section: what was done, deviations from the plan, validation/plan outcome. If no design log exists for this workstream, run `python .cursor/tools/new_design_log.py --slug <short-name>` (or fallback: create the file in `./.cursor/design-log/`), then append Implementation Results. Create logs only in `./.cursor/design-log/`. Do not consider the command complete until the log is updated.
6. **Verify:** Run `python .cursor/tools/validate_workflow_design_log.py --step implement` from the project root. If it fails, add the missing Implementation Results content and re-run the validator. Do not consider the command complete until the validator passes.

Do not add new providers or modules beyond the design log unless the user explicitly asks.
