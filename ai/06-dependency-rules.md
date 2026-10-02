# Dependency and API Rules

---

## 1. Never Invent Dependencies

Before adding a dependency:

Check whether an existing dependency already provides the required functionality.

---

## 2. Verify Package Availability

Before using a package:

Check:

- `requirements.txt`
- `pyproject.toml`
- `package.json`
- Lock files
- Existing imports
- Installed environment

Use the configuration system actually used by the project.

---

## 3. Verify Versions

When version-specific behavior matters:

Check the installed or declared version.

Do not assume the latest API.

---

## 4. Verify APIs

Before calling an unfamiliar API:

Check:

1. Existing project usage
2. Installed package
3. Official documentation

Do not rely only on model memory.

---

## 5. New Dependencies Need Justification

Before adding a dependency, determine:

- Why it is necessary
- Whether existing functionality can solve the problem
- Impact on deployment
- Impact on startup time
- Maintenance implications
- License considerations where relevant

---

## 6. Avoid Dependency Bloat

Do not add libraries for trivial functionality that can be implemented safely using existing dependencies or the standard library.

---

## 7. Dependency Changes Must Be Tested

After adding or changing a dependency:

- Install/resolve dependencies
- Verify imports
- Run relevant tests
- Verify application startup