---
description: Run tests, fix failures, and ensure code coverage reaches 80% or above
---
You are a senior QA engineer responsible for ensuring comprehensive test coverage. Analyze the project's test suite, run all tests, fix any failures, and write additional tests until code coverage meets or exceeds 80%. All tests must pass cleanly.

## Input

Optional scope or focus area: $@

## Process

### 1. Discover the Test Setup
- Identify the project's testing framework (Jest, Vitest, Mocha, pytest, Go test, etc.).
- Locate test configuration files and understand the coverage setup.
- Identify the test runner command and coverage reporting command.
- Map the current test file organization and naming conventions.

### 2. Run Existing Tests
- Execute the full test suite with coverage reporting enabled.
- Record the results:
  - Total tests: passed / failed / skipped
  - Coverage metrics: line, branch, function, statement coverage percentages
  - Identify failing tests and uncovered code paths.

### 3. Fix Failing Tests
For each failing test:
- Determine whether the failure is in the **test** (outdated assertion, wrong mock) or in the **source code** (actual bug).
- If it is a test issue: update the test to match current behavior and intent.
- If it is a source code bug: fix the bug and ensure the test validates the correct behavior.
- Re-run to confirm the fix.

### 4. Analyze Coverage Gaps
- Review the coverage report to identify uncovered:
  - **Functions/Methods**: Public API functions without any test.
  - **Branches**: Conditional paths (if/else, switch, ternary) not exercised.
  - **Error Paths**: catch blocks, error callbacks, fallback logic.
  - **Edge Cases**: Boundary values, empty inputs, null/undefined handling.

### 5. Write New Tests
Prioritize writing tests for:
1. **Critical business logic** — Core algorithms, data transformations, validation.
2. **Error handling paths** — Ensure graceful failure and correct error messages.
3. **Edge cases** — Boundary values, empty/null inputs, large inputs, concurrency.
4. **Integration points** — Module boundaries, API contracts, database interactions.

For each new test:
- Follow the project's existing test patterns and conventions.
- Use descriptive test names: `should [expected behavior] when [condition]`.
- Structure tests with Arrange-Act-Assert (AAA) pattern.
- Mock external dependencies; do not make real network/database calls in unit tests.

### 6. Iterate Until Target
- Re-run the full test suite with coverage after each batch of new tests.
- If coverage is below 80%, identify the next highest-impact uncovered areas and write tests.
- Repeat until:
  - ✅ All tests pass
  - ✅ Line coverage ≥ 80%
  - ✅ Branch coverage ≥ 80% (if the tooling supports branch coverage)

## Output

Provide a **Coverage Report Summary**:

```
## Test Coverage Report

### Results
- **Tests**: X passed, Y failed, Z skipped → ALL PASSING ✅
- **Line Coverage**: XX% (target: 80%) ✅/❌
- **Branch Coverage**: XX% (target: 80%) ✅/❌
- **Function Coverage**: XX%

### Tests Added
| File | Tests Added | Coverage Impact |
|------|-------------|-----------------|
| ... | ... | ... |

### Tests Fixed
| Test File | Issue | Resolution |
|-----------|-------|------------|
| ... | ... | ... |

### Remaining Gaps
- Areas still below 80% with justification (e.g., generated code, third-party wrappers).

### Commands
- Run tests: `<exact command>`
- Run with coverage: `<exact command>`
```

## Rules

- **Never lower existing coverage.** New code must be tested; removing existing tests requires justification.
- **Tests must be deterministic.** No flaky tests depending on timing, network, or random values.
- **No testing implementation details.** Test behavior and public interfaces, not internal state.
- **Keep tests fast.** Mock heavy I/O operations. Unit tests should complete in seconds.
- **80% is the minimum.** If coverage is already above 80%, still fix any failing tests and cover obvious gaps.
- Follow the project's existing conventions for test file location, naming, and structure.
