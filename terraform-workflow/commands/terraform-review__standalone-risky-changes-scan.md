# Risky changes scan (Standalone)

Flag risky patterns: sensitive data exposure, state impact, new providers, breaking changes.

## Steps

1. **Scan** the changed files (or the whole codebase if the user does not specify) for:
   - **Sensitive data:** Outputs or variables that might expose secrets; missing `sensitive = true`; values that could appear in plan/logs.
   - **State impact:** Resource identifier changes (name, key) that could cause destroy/recreate; missing `moved` blocks where a rename was intended.
   - **New providers or modules:** Any new provider or module sources. Note version and why they are needed.
   - **Breaking changes:** Input/output contract changes that could break callers; resource renames or removals.
2. **Report:** For each category, list occurrences with file/line or a short reference. Summarize overall risk (low / medium / high) and recommend follow-up (e.g. "add moved block", "mark output sensitive", "document breaking change").

Do not fix the code in this command unless the user asks; focus on identification and prioritization.
