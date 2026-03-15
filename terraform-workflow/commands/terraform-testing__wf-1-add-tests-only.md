# Add tests / verification only (terraform-testing WF Step 1)

Add or extend verification (e.g. plan checks, terraform test, CI checks) only. No production Terraform config changes. Justify what is being checked. You can use this command on its own — no requirement to run design-review or implementation first.

## Steps

1. **Scope:** Identify what behavior or module needs more verification. Confirm with the user if unclear.
2. **Verification only:** Add or edit only test/verification code or config (e.g. terraform test files, plan assertions). Do not change main Terraform configuration unless necessary for test setup.
3. **Justify:** For each new check, state what it covers (e.g. "no unexpected destroy", "sensitive not in output").
4. **Verification:** Run `terraform fmt -recursive`, `terraform validate`; if the project uses terraform test or similar, run those. Ensure existing checks still pass.
5. **Record in design log (mandatory):** Append a **Test session** section to the design log for this workstream: what was covered, how verification was run, any failures fixed. If no log exists, run `python .cursor/tools/new_design_log.py --slug <short-name>` (or fallback: create the file in `./.cursor/design-log/`), then add the Test session content. Create logs only in `./.cursor/design-log/`. Do not ask — do it.
6. **Verify:** Run `python .cursor/tools/validate_workflow_design_log.py --step add-tests` from the project root. If it fails, add the missing Test session content and re-run the validator. Do not consider the command complete until the validator passes.

If the desired verification requires production config changes, say so and suggest a separate task.
