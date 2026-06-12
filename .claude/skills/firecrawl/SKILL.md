```markdown
# firecrawl Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill covers the core development patterns and conventions used in the `firecrawl` TypeScript codebase. It documents file naming, import/export styles, commit message conventions, and testing patterns. Whether you're contributing new features or maintaining the code, following these guidelines will ensure consistency and quality across the project.

## Coding Conventions

### File Naming

- Use **kebab-case** for all file names.
  - Example:  
    ```
    firecrawl-core.ts
    data-fetcher.test.ts
    ```

### Import Style

- Always use **relative imports**.
  - Example:
    ```typescript
    import { fetchData } from './data-fetcher';
    ```

### Export Style

- Use **named exports** (avoid default exports).
  - Example:
    ```typescript
    // In data-fetcher.ts
    export function fetchData(url: string): Promise<any> { ... }
    ```

    ```typescript
    // In another file
    import { fetchData } from './data-fetcher';
    ```

### Commit Messages

- Follow **conventional commit** style.
- Use clear prefixes such as `chore`.
- Keep messages concise (average ~76 characters).
  - Example:
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

_No automated workflows detected in this repository._

## Testing Patterns

- Test files use the pattern: `*.test.*`
  - Example: `firecrawl-core.test.ts`
- The testing framework is not specified; check project documentation or package.json for details.
- Place tests alongside implementation files or in a dedicated test directory as appropriate.

  ```typescript
  // Example: firecrawl-core.test.ts
  import { fetchData } from './firecrawl-core';

  describe('fetchData', () => {
    it('should return data for a valid URL', async () => {
      const data = await fetchData('https://example.com');
      expect(data).toBeDefined();
    });
  });
  ```

## Commands

| Command   | Purpose                                      |
|-----------|----------------------------------------------|
| /test     | Run all tests in the repository              |
| /lint     | Lint the codebase for style and errors       |
| /commit   | Start a commit using the conventional format |
```