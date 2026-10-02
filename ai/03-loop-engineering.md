# Loop Engineering Workflow

All meaningful development tasks should follow this cycle.

---

# Phase 1: INSPECT

Understand the current repository.

Tasks:

- Inspect structure
- Find relevant files
- Search implementations
- Inspect dependencies
- Inspect tests
- Trace execution

Output:

A verified understanding of the current state.

---

# Phase 2: UNDERSTAND

Determine:

- Current behavior
- Expected behavior
- Actual problem
- Constraints
- Dependencies
- Side effects

Separate facts from assumptions.

---

# Phase 3: MEASURE

Measure the current state when relevant.

Examples:

- Test count
- Runtime
- Startup time
- Memory
- File size
- Model metrics
- UI behavior
- Error frequency

Establish a baseline before optimization.

---

# Phase 4: PLAN

Create the smallest reasonable implementation plan.

Include:

1. Files to change
2. Files to create
3. Logic changes
4. Tests required
5. Risks
6. Verification method

Do not create speculative architecture.

---

# Phase 5: IMPLEMENT

Implement the approved solution.

Rules:

- Keep changes focused.
- Follow existing patterns.
- Avoid unrelated refactoring.
- Preserve working behavior.
- Do not introduce unnecessary dependencies.

---

# Phase 6: TEST

Run appropriate tests.

Examples:

- Unit tests
- Integration tests
- Import checks
- Syntax checks
- Type checks
- Application startup
- Relevant user flow

---

# Phase 7: VERIFY

Confirm that the requested behavior actually works.

Do not rely solely on tests if runtime behavior matters.

---

# Phase 8: REVIEW

Review the implementation for:

- Bugs
- Regression risks
- Unnecessary complexity
- Security issues
- Performance problems
- Duplicate logic
- Missing tests

---

# Phase 9: FIX

If verification finds a problem:

Fix it.

Then repeat testing and verification.

---

# Phase 10: FINAL AUDIT

Before declaring completion:

- Check changed files
- Run relevant tests
- Review diff
- Confirm requirements
- Identify remaining issues

---

# Loop

INSPECT
↓
UNDERSTAND
↓
MEASURE
↓
PLAN
↓
IMPLEMENT
↓
TEST
↓
VERIFY
↓
REVIEW
↓
FIX
↓
AUDIT

Never skip verification simply because the change appears obvious.