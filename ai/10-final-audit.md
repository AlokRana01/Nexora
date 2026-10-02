# Final Audit Rules

This document defines the final gate before an AI agent declares a task complete.

---

# 1. Requirement Check

Verify every requested requirement.

For each requirement:

- DONE AND VERIFIED
- DONE BUT NOT FULLY VERIFIED
- NOT DONE
- BLOCKED

Do not mark something verified without evidence.

---

# 2. Code Review

Review all modified files.

Check:

- Correctness
- Readability
- Duplication
- Error handling
- Security
- Performance
- Maintainability
- Unnecessary complexity

---

# 3. Diff Review

Inspect the actual changes.

Look for:

- Accidental edits
- Debug code
- Temporary files
- Unused imports
- Unused variables
- Unrelated changes
- Hardcoded values
- Secrets
- Dead code

---

# 4. Test Review

Confirm:

- Relevant tests were executed
- New behavior is tested
- Regression risks were considered
- Failures are reported

---

# 5. Runtime Review

When relevant, verify actual runtime behavior.

Do not rely exclusively on static inspection.

---

# 6. Documentation Review

If behavior, configuration, architecture, or setup changed:

Update relevant documentation when necessary.

Do not create documentation that describes unverified behavior.

---

# 7. Hallucination Audit

Before final response, ask:

Did I invent anything?

Check:

- Files
- Functions
- APIs
- Dependencies
- Results
- Metrics
- Test status
- Architecture claims

If something was not verified, clearly label it.

---

# 8. Final Status

Use this structure:

## Verified

List what was directly confirmed.

## Changed

List actual modifications.

## Tested

List exact tests or commands executed.

## Not Verified

List anything that could not be confirmed.

## Remaining Issues

List unresolved problems.

## Final Status

Use one:

COMPLETE
COMPLETE WITH LIMITATIONS
BLOCKED
NOT COMPLETE

Do not use COMPLETE if important requirements remain unverified.

---

# Final Rule

Never declare success because the code looks correct.

Declare success only after evidence supports it.