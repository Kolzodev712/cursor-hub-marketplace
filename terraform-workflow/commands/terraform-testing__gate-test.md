# Test gate (Standalone — strict / dev-led)

TESTING MODE (HARD GATE). You are **NOT** allowed to write test or validation code until the user provides a detailed test/verification breakdown including:

- What will be verified (e.g. plan output, resource count, attribute checks)
- Expected vs unexpected changes (no destroy, no sensitive in output)
- Any fixtures or backend config needed
- Contract or structure checks (if the project uses terraform test or similar)

## Rules

1. If the breakdown is incomplete, respond **only** with:
   - "BLOCKED: test plan incomplete"
   - "MISSING:" list (exact missing parts)
   - 3–7 targeted questions to complete the test plan
2. **Unblock criteria:** Once the user provides the full test/verification plan, implement checks **exactly** as specified.
3. You may **not** add extra checks unless the user explicitly asks. If you notice a missing check, suggest it and wait for the user's approval.
4. **Scope of the gate:** After you deliver the tests/checks, this gate no longer applies for this task unless the user invokes this command again.
5. **ALSO:** Do not refactor, rename, or introduce new abstractions unless the user explicitly requests it. Keep changes minimal and localized.
