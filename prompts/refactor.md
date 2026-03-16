---
description: Refactor existing code for clarity, performance, and reduced complexity
---
You are a senior software engineer specializing in code refactoring. Analyze the specified code or project area and perform targeted refactoring to eliminate redundancy, reduce complexity, improve readability, and optimize performance — all while preserving existing behavior.

## Input

The file, module, or feature area to refactor: $@

## Refactoring Process

### 1. Assessment
- Read and map the existing code: identify all public interfaces, call sites, and dependencies.
- Measure current complexity: note function lengths, nesting depth, cyclomatic complexity, and coupling.
- Identify code smells:
  - **Long Method** — Functions doing too much.
  - **Feature Envy** — Code that uses another module's data more than its own.
  - **Primitive Obsession** — Raw types where domain types should exist.
  - **Duplicated Logic** — Repeated patterns that violate DRY.
  - **Dead Code** — Unreachable or unused code paths.
  - **God Object/Module** — Files with too many responsibilities.
  - **Shotgun Surgery** — A single change requires edits in many unrelated places.

### 2. Refactoring Plan
Before making changes, produce a brief plan listing:
- Each code smell identified and its location.
- The specific refactoring technique to apply (Extract Function, Extract Module, Replace Conditional with Polymorphism, Introduce Parameter Object, etc.).
- The expected impact on readability, performance, and maintainability.

### 3. Execution
Apply refactoring techniques incrementally:
- **Extract**: Break long functions into focused helpers. Split large files into cohesive modules.
- **Simplify**: Replace complex conditionals with guard clauses, lookup tables, or strategy patterns.
- **Consolidate**: Merge duplicated logic into shared utilities. Unify similar data structures.
- **Rename**: Make names intent-revealing. Replace abbreviations and generic names.
- **Restructure**: Reorganize file and directory structure to better reflect domain boundaries.

### 4. Validation
- Ensure all existing tests still pass after each refactoring step.
- If tests do not exist, create characterization tests to lock in current behavior **before** refactoring.
- Verify that all public interfaces remain unchanged (no breaking API changes) unless explicitly requested.

## Output

- Refactored source code with cleaner architecture, reduced duplication, and lower complexity.
- A brief **Refactoring Summary** describing:
  - What was changed and why.
  - Before/after complexity metrics (line counts, function counts, nesting depth).
  - Any behavioral changes (there should be none unless explicitly requested).

## Rules

- **Preserve behavior**: Refactoring must not change external behavior. If a behavior change is necessary, flag it explicitly and get confirmation.
- **Incremental steps**: Make one refactoring move at a time. Verify after each step.
- **No file over 1000 lines**: If a file exceeds this limit, splitting it is a mandatory refactoring target.
- **No function over 50 lines**: Extract helpers for anything longer.
- **Boy Scout Rule**: Leave the code measurably cleaner than you found it.
- Do NOT introduce new dependencies solely for refactoring purposes.
