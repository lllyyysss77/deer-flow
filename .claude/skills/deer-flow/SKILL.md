```markdown
# deer-flow Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the development patterns and conventions used in the `deer-flow` Python codebase. You'll learn how to structure files, write imports and exports, follow commit conventions, and understand the project's approach to testing. This guide is ideal for contributors looking to maintain consistency and quality in their code contributions.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `data_processor.py`, `utils_helper.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import process_data
    from .models import Deer
    ```

### Export Style
- Use **named exports** (explicitly define what is exported).
  - Example:
    ```python
    __all__ = ['process_data', 'Deer']
    ```

### Commit Patterns
- Commit messages are mixed but often use the `fix` prefix for bug fixes.
- Aim for descriptive commit messages (average length: ~100 characters).
  - Example:
    ```
    fix: correct data flow in process_data to handle empty input cases
    ```

## Workflows

### Adding a New Module
**Trigger:** When you need to add new functionality as a module.
**Command:** `/add-module`

1. Create a new Python file using snake_case (e.g., `new_feature.py`).
2. Implement your functionality.
3. Use relative imports to access utilities or models.
4. Define `__all__` to specify exported names.
5. Write corresponding tests in a file matching `*.test.*`.
6. Commit changes with a descriptive message.

### Fixing a Bug
**Trigger:** When you identify and fix a bug.
**Command:** `/fix-bug`

1. Locate the bug in the relevant module.
2. Apply the fix, following code style conventions.
3. Update or add tests to cover the bug scenario.
4. Commit with a message starting with `fix:`, describing the issue and solution.

### Writing Tests
**Trigger:** When adding or modifying features.
**Command:** `/write-test`

1. Create a test file named with the pattern `*.test.*` (e.g., `utils.test.py`).
2. Write test functions for the new or changed code.
3. Use assertions to verify expected behavior.
4. Run tests using your preferred Python test runner.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `module.test.py`).
- The specific testing framework is not detected; use standard Python test frameworks (e.g., `unittest`, `pytest`).
- Place tests alongside or near the modules they cover.
- Example test structure:
  ```python
  def test_process_data_handles_empty():
      result = process_data([])
      assert result == []
  ```

## Commands
| Command      | Purpose                                  |
|--------------|------------------------------------------|
| /add-module  | Scaffold and add a new module            |
| /fix-bug     | Apply and commit a bug fix               |
| /write-test  | Create and run tests for your code       |
```
