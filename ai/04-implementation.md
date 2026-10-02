# Implementation Rules

---

## 1. Make the Smallest Correct Change

Prefer the minimum code change that solves the verified problem.

Avoid unnecessary rewrites.

---

## 2. Follow Existing Patterns

Before introducing a new pattern:

Search the repository for how similar functionality is already implemented.

Prefer consistency.

---

## 3. Avoid Duplicate Logic

Before adding a helper:

Search for existing helpers that already perform similar work.

Reuse or extend existing utilities when appropriate.

---

## 4. Preserve Public Interfaces

Do not unnecessarily change:

- Function signatures
- APIs
- Database schemas
- Routes
- Component interfaces
- Configuration contracts

If a breaking change is necessary, identify it explicitly.

---

## 5. Error Handling

Handle errors at the appropriate boundary.

Do not:

- Silently swallow exceptions
- Hide important failures
- Use broad exception handling without reason
- Return misleading success states

---

## 6. State Management

For applications with session or application state:

Understand existing state flow before changing it.

Do not introduce duplicate state sources unless necessary.

---

## 7. Configuration

Do not hardcode values that belong in configuration.

Do not expose secrets.

Do not create fake environment variables.

---

## 8. Comments

Comments should explain:

- Why something exists
- Why an unusual decision was made
- Important constraints

Do not add comments that merely restate obvious code.

---

## 9. Refactoring

Only refactor when:

- Required for the task
- Necessary to fix the verified problem
- Necessary to safely implement the feature

Do not mix unrelated refactoring into a feature change.

---

## 10. Generated Code

Review generated code exactly like human-written code.

AI-generated code is not automatically correct.