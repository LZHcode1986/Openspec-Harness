# Post-Archive Normalization Checklist

After `archive`, immediately normalize the main spec so the archive result does not pollute the spec library.

## 1. Structural integrity

- [ ] Does the archived `spec.md` still have the correct title?
- [ ] Does it contain a standalone `## Purpose` section?
- [ ] Does it contain a standalone `## Requirements` section?

## 2. Remove delta semantics

- [ ] Does the main spec still contain `## ADDED Requirements`, `## MODIFIED Requirements`, or similar delta headings?
- [ ] Do requirement descriptions still use delta-style wording such as "this change updates..."?

## 3. Remove placeholders

- [ ] Is `Purpose` still placeholder text?
- [ ] Do `Requirements` still contain unfilled template placeholders?

## 4. Independent readability

- [ ] Can the merged main spec describe the current system behavior without referring back to the archived change?

## 5. Validation

- [ ] Has the project-specific `openspec validate --all --strict` or an equivalent validation command passed?

