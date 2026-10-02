# AI Engineering Rules

This folder contains the engineering rules and operating procedures that AI coding agents must follow when working on this repository.

The purpose of these documents is to make AI-assisted development:

- Evidence-driven
- Consistent
- Verifiable
- Maintainable
- Secure
- Resistant to hallucination
- Resistant to unnecessary rewrites
- Test-driven
- Repository-aware

## Instruction Hierarchy

Read and follow the documents in this order:

1. `00-core-rules.md`
2. `01-anti-hallucination.md`
3. `02-repository-inspection.md`
4. `03-loop-engineering.md`
5. `04-implementation.md`
6. `05-testing-verification.md`
7. `06-dependency-rules.md`
8. `07-performance-rules.md`
9. `08-ui-ux-rules.md`
10. `09-security-rules.md`
11. `10-final-audit.md`

These documents are complementary.

If two instructions appear to conflict, follow the more specific rule for the current task while preserving the core rules.

---

# Core Principle

The repository is the source of truth.

Do not trust assumptions, memory, previous AI responses, generated summaries, comments, TODOs, or imagined architecture without verification.

The required workflow is:

INSPECT
→ UNDERSTAND
→ MEASURE
→ PLAN
→ IMPLEMENT
→ TEST
→ VERIFY
→ REVIEW
→ FIX
→ AUDIT

---

# Important Rule

Never guess when the repository can be inspected.

Never claim something works unless it has been verified.

Never claim a test passed unless it was actually executed.

Never invent files, APIs, functions, dependencies, configuration values, benchmark results, or implementation details.

---

# Task-Specific Rules

Not every rule applies equally to every task.

For example:

- UI task → read `08-ui-ux-rules.md`
- Performance task → read `07-performance-rules.md`
- Security task → read `09-security-rules.md`
- Dependency/API task → read `06-dependency-rules.md`

However, `00-core-rules.md` and `01-anti-hallucination.md` always apply.

---

# Final Principle

AI should behave as an engineering assistant, not as an authority.

Evidence first.
Changes second.
Verification always.