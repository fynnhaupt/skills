---
name: testing
description: Write tests red → green, one slice at a time, at agreed seams. Use when building a feature or fixing a bug test-first, or when another skill needs code driven by tests.
---

# Testing

Drive code with tests: each test fails first, then just enough code makes it pass. Tests check **behaviour** through public interfaces, so they survive any refactor that keeps the behaviour.

A **seam** is a public interface where you observe behaviour without reaching inside. Tests live at seams only.

If the project has no test runner, tell the user and stop; this skill does not set one up.

## Steps

1. **Agree the seams.** Take them from the spec's approach, if the work has a spec that names them. Otherwise propose seams on the critical paths and complex logic, and confirm them with the user. Done when every seam you will test is named and agreed.
2. **Read [TESTS.md](TESTS.md) and [MOCKING.md](MOCKING.md)** before the first test. Done when you have read both.
3. **Loop red → green**, one slice per cycle: write one test at a seam, run it and see it fail for the expected reason, then write only enough code to make it pass. For a bug, the first test reproduces it. Let each test build on what the last cycle taught you, rather than writing all tests up front. Name tests in the project's domain words. Done when every behaviour the work needs has a passing test at a seam, and all tests of the work pass together.

Refactoring stays out of the loop; it belongs to review.
