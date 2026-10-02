# Core Engineering Rules

These rules apply to every task.

---

## 1. Repository Is the Source of Truth

The current repository is authoritative.

Do not assume that previous conversations, previous AI responses, documentation, comments, TODOs, or generated summaries accurately describe the current implementation.

Verify against the actual repository.

---

## 2. Never Guess

If something is unknown, inspect it.

Do not guess:

- File paths
- Function names
- Class names
- Variables
- APIs
- Dependencies
- Configuration
- Framework behavior
- Test results
- Performance results
- Existing features
- Architecture
- User flows

Use repository inspection or execution to determine the answer.

---

## 3. Evidence Before Action

Before making meaningful changes:

1. Inspect relevant files.
2. Search for related implementations.
3. Trace imports and dependencies.
4. Inspect configuration.
5. Inspect tests.
6. Understand current behavior.
7. Identify the actual problem.
8. Then plan the change.

---

## 4. Preserve Existing Architecture

Do not redesign the application unless the task requires it.

Prefer:

- Small changes
- Localized changes
- Existing utilities
- Existing abstractions
- Existing patterns
- Existing architecture

Avoid unnecessary rewrites.

---

## 5. Do Not Expand Scope

Only implement what the task requires.

Do not silently add:

- New features
- New dependencies
- New architecture
- New UI systems
- New abstractions
- Unrequested refactors

If an additional change is necessary, explain why.

---

## 6. No Unverified Claims

Never say:

- "Fixed"
- "Working"
- "Completed"
- "Optimized"
- "Production ready"
- "Secure"
- "All tests pass"

unless the appropriate verification has actually been performed.

---

## 7. Prefer Reversible Changes

When possible:

- Make small commits
- Keep changes localized
- Avoid destructive migrations
- Avoid deleting working code without evidence
- Preserve backwards compatibility when practical

---

## 8. Explain Uncertainty

Use explicit labels:

FACT:
Directly verified.

INFERENCE:
Reasonably derived from verified evidence.

UNKNOWN:
Not yet verified.

Do not disguise assumptions as facts.

---

## 9. Quality Over Speed

A fast incorrect implementation is worse than a slower verified implementation.

Optimize for correctness first.

---

## 10. Final Rule

When uncertain:

STOP → INSPECT → VERIFY → CONTINUE