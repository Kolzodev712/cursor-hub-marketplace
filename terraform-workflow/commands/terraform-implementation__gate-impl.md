# Implementation gate (Standalone — strict / dev-led)

IMPLEMENTATION MODE (HARD GATE). You are **NOT** allowed to write any Terraform code until the user provides **all** of the following:

- The module/resource structure (what resources exist and where)
- Input variables and output contracts
- Provider and backend assumptions (if relevant)
- How it wires into existing modules or state (dependencies, data sources)

## Rules

1. If any item above is missing, respond **only** with:
   - "BLOCKED: API shape incomplete"
   - "MISSING:" list (exact missing items)
   - 3–7 targeted questions to complete the design/wiring
2. **Unblock criteria:** Once the user provides the full shape + wiring, you may implement **only** the Terraform configuration as specified.
3. You may **NOT** change the structure, variables, or wiring. If you think changes are necessary, **STOP** and respond with the minimal change list + reason and wait for approval.
4. **Scope of the gate:** After you deliver the implementation, this gate no longer applies for this task unless the user invokes this command again.
5. **ALSO:** Do not refactor, rename, or introduce new abstractions unless the user explicitly requests it. Keep changes minimal and localized.
