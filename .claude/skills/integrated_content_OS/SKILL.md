```markdown
# integrated_content_OS Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and automated workflows used in the `integrated_content_OS` TypeScript codebase. You'll learn how to structure files, write and organize code, manage dependencies across multiple packages, and understand the project's testing approach.

## Coding Conventions

- **Language:** TypeScript
- **Framework:** None detected

### File Naming
- Use **camelCase** for file names.
  - Example: `contentManager.ts`, `userProfileService.ts`

### Imports
- Use **relative import paths**.
  - Example:
    ```typescript
    import { fetchContent } from './contentFetcher';
    ```

### Exports
- Use **named exports**.
  - Example:
    ```typescript
    // contentFetcher.ts
    export function fetchContent() { ... }
    ```

### Commit Messages
- Freeform style, no strict prefixing.
- Average commit message length: 64 characters.

## Workflows

### Dependency Update Across Multiple Packages
**Trigger:** When dependencies need to be kept up-to-date across multiple packages or workspaces in a monorepo.
**Command:** `/update-dependencies`

1. Detect outdated dependencies in all relevant `package.json` files.
2. Update the version(s) of the dependency in each `package.json`.
3. Update the corresponding `package-lock.json` files.
4. Commit all changed `package.json` and `package-lock.json` files together.

**Files involved:**
- `**/package.json`
- `**/package-lock.json`

**Example:**
```sh
# Run the update command (if supported by tooling)
npm update

# Or manually update versions, then:
git add **/package.json **/package-lock.json
git commit -m "Update dependencies across packages"
```

## Testing Patterns

- **Test Files:** Identified by the pattern `*.test.*` (e.g., `contentManager.test.ts`)
- **Testing Framework:** Not explicitly detected; check for test runner in the project (e.g., Jest, Mocha).
- **Test Example:**
    ```typescript
    // contentManager.test.ts
    import { fetchContent } from './contentManager';

    test('fetchContent returns expected data', () => {
      expect(fetchContent()).toEqual(expectedData);
    });
    ```

## Commands

| Command              | Purpose                                                    |
|----------------------|------------------------------------------------------------|
| /update-dependencies | Update npm dependencies across all packages in the monorepo |
```
