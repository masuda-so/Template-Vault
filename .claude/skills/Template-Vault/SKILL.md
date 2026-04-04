```markdown
# Template-Vault Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns used in the Template-Vault repository, a TypeScript codebase with no detected framework. You'll learn about file naming, import/export conventions, commit patterns, and how to write and run tests. The guide also provides suggested commands for common workflows to streamline your development process.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myComponent.ts`, `userService.test.ts`

### Import Style
- Use **relative imports** for referencing other modules.
  - Example:
    ```typescript
    import { helperFunction } from './utils/helperFunction';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // In utils/helperFunction.ts
    export function helperFunction() { ... }

    // In another file
    import { helperFunction } from './utils/helperFunction';
    ```

### Commit Patterns
- Commit types are **mixed**, but commonly use the `feat` prefix for new features.
- Commit messages average **46 characters** in length.
  - Example: `feat: add user authentication middleware`

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new feature or module  
**Command:** `/add-feature`

1. Create a new file using camelCase naming (e.g., `newFeature.ts`).
2. Use relative imports to include dependencies.
3. Export your functions or classes using named exports.
4. Write corresponding tests in a file named `newFeature.test.ts`.
5. Commit your changes with a message starting with `feat:`, e.g., `feat: implement new feature logic`.

### Writing and Running Tests
**Trigger:** When adding or updating functionality  
**Command:** `/run-tests`

1. Create a test file with the pattern `*.test.ts` (e.g., `userService.test.ts`).
2. Write tests for your functions or classes.
3. Use the project's preferred test runner (framework not specified; check project documentation or package.json).
4. Run your tests to ensure all pass before committing.

### Refactoring Code
**Trigger:** When improving or restructuring existing code  
**Command:** `/refactor`

1. Identify code to refactor.
2. Update file names to camelCase if needed.
3. Adjust imports/exports to maintain relative and named conventions.
4. Update or add tests as necessary.
5. Commit with a descriptive message, e.g., `refactor: optimize user data processing`.

## Testing Patterns

- Test files follow the `*.test.ts` naming convention.
- The testing framework is **unknown**; check the project documentation or `package.json` for details.
- Example test file:
  ```typescript
  // userService.test.ts
  import { getUser } from './userService';

  describe('getUser', () => {
    it('should return user data for a valid ID', () => {
      const user = getUser(1);
      expect(user).toBeDefined();
    });
  });
  ```

## Commands

| Command       | Purpose                                      |
|---------------|----------------------------------------------|
| /add-feature  | Scaffold and commit a new feature/module     |
| /run-tests    | Run all test files matching `*.test.ts`      |
| /refactor     | Refactor code and update related tests       |
```