# Testing and Verification Rules

Testing is required whenever behavior changes.

---

## 1. Test the Changed Area

Tests should target the actual behavior modified.

Do not run unrelated tests and use them as evidence that the change works.

---

## 2. Start With Focused Tests

First run the smallest relevant test set.

Then expand to broader tests when appropriate.

Example:

Specific test
→ Module tests
→ Integration tests
→ Full suite

---

## 3. Test Failures Are Evidence

When a test fails:

Do not immediately modify the test to make it pass.

First determine:

- Why it failed
- Whether the implementation is wrong
- Whether the test is outdated
- Whether the environment is wrong

---

## 4. Do Not Fake Tests

Never:

- Create fake test output
- Claim a command was executed when it was not
- Remove assertions just to pass
- Disable failing tests without justification
- Change expected values without understanding the behavior

---

## 5. Regression Testing

When fixing a bug:

Add or update a regression test when practical.

The test should reproduce the original failure and prove the fix.

---

## 6. Runtime Verification

For runtime-sensitive changes:

Actually run the relevant application or execution path.

Examples:

- UI changes
- Startup changes
- Routing
- Session state
- Database behavior
- Model inference
- File processing

---

## 7. Final Test Report

Report:

### Tests Run
Exact tests or commands.

### Result
Pass/fail and relevant counts.

### Runtime Verification
What was manually or programmatically verified.

### Remaining Failures
Any known failures.

Never hide failing tests.