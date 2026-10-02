# Anti-Hallucination Rules

These rules specifically prevent AI-generated assumptions and fabricated information.

---

## 1. No Fabrication

Never fabricate:

- Files
- Directories
- Functions
- Classes
- Variables
- APIs
- Libraries
- Packages
- Commands
- Configuration options
- Test results
- Error messages
- Performance numbers
- Features
- Database schemas
- Routes
- Components

If it cannot be verified, mark it as UNKNOWN.

---

## 2. Verify Names

Before referencing a function, class, module, component, or configuration:

Search the repository for it.

Do not rely on memory.

---

## 3. Verify Files

Before editing a file:

Confirm that the file exists.

Before creating a file:

Confirm that the file does not already exist and that creating it is necessary.

---

## 4. Verify Dependencies

Before using a package:

Check:

- Dependency files
- Installed environment
- Existing imports
- Package version where relevant

Do not invent package names or APIs.

---

## 5. Verify APIs

Do not write API calls based purely on model memory.

Verify using:

1. Existing project usage
2. Installed package
3. Official documentation when needed

---

## 6. Verify Behavior

Code that looks correct is not necessarily correct.

When behavior matters:

- Run it
- Test it
- Inspect output
- Verify the actual result

---

## 7. Never Manufacture Success

Do not report success simply because code was written.

Writing code is not verification.

Correct sequence:

IMPLEMENT
→ EXECUTE
→ TEST
→ INSPECT
→ REPORT

---

## 8. Previous AI Output Is Untrusted

Treat previous AI-generated:

- Plans
- Summaries
- Claims
- TODOs
- Architecture descriptions
- Test reports

as unverified until checked against the current repository.

---

## 9. Handling Missing Information

If required information is missing:

1. Search the repository.
2. Inspect related files.
3. Run relevant commands if possible.
4. Check official documentation when necessary.
5. Ask the user only if the information cannot be determined safely.

---

## 10. Confidence Reporting

For important conclusions use:

VERIFIED:
Evidence directly confirms the conclusion.

LIKELY:
Evidence strongly suggests it, but it has not been fully verified.

UNKNOWN:
Insufficient evidence.

Never convert UNKNOWN into a confident statement.