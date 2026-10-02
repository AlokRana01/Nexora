# UI/UX Engineering Rules

UI changes must be verified through actual application behavior whenever practical.

---

## 1. Inspect Existing UI First

Before modifying UI:

Identify:

- Layout system
- Navigation
- Components
- Theme
- Typography
- State handling
- Responsive behavior
- Existing design system

---

## 2. Preserve Design Language

Do not introduce unrelated visual styles.

Follow the existing:

- Typography
- Spacing
- Radius
- Shadows
- Components
- Color system
- Interaction patterns

---

## 3. Avoid UI Clutter

Do not add UI elements merely because they are technically possible.

Every visible element should have a purpose.

Prioritize:

- Clear hierarchy
- Discoverability
- Readability
- Consistent spacing
- Simple workflows

---

## 4. Do Not Assume Visual Success

Code inspection alone cannot guarantee visual correctness.

When practical:

1. Run the application.
2. Navigate to the affected screen.
3. Verify rendering.
4. Verify interactions.
5. Check relevant states.

---

## 5. Responsive Behavior

When relevant, verify:

- Desktop
- Smaller viewport
- Long content
- Empty state
- Error state
- Loading state

---

## 6. Accessibility

Consider:

- Readable contrast
- Keyboard accessibility where applicable
- Clear labels
- Error messages
- Focus states
- Semantic structure

---

## 7. Loading and Error States

Every asynchronous or expensive operation should have appropriate:

- Loading state
- Success state
- Error state
- Empty state where applicable

Do not leave the user with ambiguous UI.

---

## 8. UI Performance

Avoid unnecessary:

- Re-renders
- Expensive calculations
- Duplicate data loading
- Large DOM/component trees
- Repeated model operations

Measure when performance is a concern.

---

## 9. No Fake UX Verification

Do not claim:

"Looks perfect"

based only on generated code.

Report what was actually verified.