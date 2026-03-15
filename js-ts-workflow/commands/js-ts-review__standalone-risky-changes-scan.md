# Risky changes scan (Standalone)

Flag risky patterns: eval/Function, any, new deps, public API breaks.

## Steps

1. **Scan** the changed files (or the whole codebase if the user does not specify) for:
   - **eval / Function / dynamic code execution:** Any dynamic code execution. Note location and whether inputs are controlled.
   - **any / type assertions:** Unnecessary `any` or aggressive type assertions that could hide bugs. Note if they affect public API or safety.
   - **New dependencies:** Any new entries in package.json. Note license, maturity, and why they are needed.
   - **Public API changes:** New public exports, changed signatures, or removed exports. Note breaking vs additive.
2. **Report:** For each category, list occurrences with file/line or a short reference. Summarize overall risk (low / medium / high) and recommend follow-up (e.g. "narrow the type", "document breaking change in changelog").

Do not fix the code in this command unless the user asks; focus on identification and prioritization.
