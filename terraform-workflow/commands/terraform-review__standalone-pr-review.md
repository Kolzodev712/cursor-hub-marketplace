# PR review (Standalone)

File-by-file review of Terraform changes with "must-fix" vs "nice-to-have" findings.

## Steps

1. **Scope:** Identify the set of files or diffs to review (e.g. from a PR description, or the user will point to files).
2. **Per file:** Walk through each changed file. For each:
   - **Correctness:** Valid HCL; no unintended destroy/replace from identifier changes?
   - **State and lifecycle:** moved blocks, lifecycle rules used correctly and documented?
   - **Sensitive data:** No secrets in code; sensitive outputs/variables marked?
   - **Providers:** Versions and required_providers consistent?
   - **Style:** Formatted with terraform fmt; clear naming?
   - **Security:** No hardcoded credentials; least-privilege considered?
3. **Classify:** For each finding, label **must-fix** (correctness, safety, state integrity) or **nice-to-have** (style, clarity).
4. **Summary:** List must-fix items first, then nice-to-have. Suggest concrete changes where helpful.

Keep the review actionable. Quote file/line or snippet when referring to a finding.
