# Repository Inspection Rules

Never modify code blindly.

---

## 1. Inspect Before Editing

Before implementation, inspect:

- Project structure
- Relevant source files
- Configuration
- Dependencies
- Tests
- Related modules
- Existing utilities

---

## 2. Find the Real Implementation

Do not assume the obvious filename contains the implementation.

Search for:

- Function definitions
- Class definitions
- Imports
- Calls
- Routes
- Components
- Configuration references
- Related tests

Trace the actual execution path.

---

## 3. Understand Data Flow

For data-related tasks identify:

INPUT
→ VALIDATION
→ TRANSFORMATION
→ PROCESSING
→ OUTPUT

For UI tasks identify:

USER ACTION
→ STATE
→ LOGIC
→ RENDERING
→ RESULT

For ML tasks identify:

DATA
→ PREPROCESSING
→ TRAINING
→ VALIDATION
→ PREDICTION
→ EXPLANATION

---

## 4. Inspect Tests

Before changing behavior:

Find existing tests.

Understand:

- What is currently tested
- What assumptions tests make
- What behavior is expected
- Whether regression tests are needed

---

## 5. Check Configuration

Inspect relevant:

- `.env` examples
- Configuration files
- Dependency files
- Build files
- Framework configuration
- Deployment configuration

Never assume configuration values.

---

## 6. Search Before Creating

Before creating a utility, helper, component, or abstraction:

Search the repository for an existing equivalent.

Prefer reuse when appropriate.

---

## 7. Identify Side Effects

Before changing shared code, identify:

- Callers
- Imports
- State dependencies
- Database effects
- File effects
- Caching
- Session state
- UI dependencies
- External API calls

---

## 8. Inspection Report

For complex tasks, produce a concise internal assessment:

### Current Implementation
What exists.

### Relevant Files
Exact files involved.

### Execution/Data Flow
How the feature currently works.

### Problem
What is actually wrong.

### Constraints
What must not be changed.

### Proposed Change
What should be modified.

Do not implement until the problem is understood.