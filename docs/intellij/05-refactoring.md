# IntelliJ 05 - Refactor and verify Java code

[Previous: unit tests](04-unit-tests.md) | [Java track](../tracks/java.md) | [Next: web prototype](06-vibe-coding.md)

**Not battle tested; partially applicable to the inspected starter.** Adapted from [Java exercise 05](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_05_refactor_improve_existing_code_java.md); see [sources and attribution](SOURCES.md). Goal: analyze existing behavior, make justified refactorings, and demonstrate behavior preservation.

## Mandatory applicability checkpoint

At source revision `d1973fb8605634150a17facef7b819d3d567c4e7`, the Java application differs from the original exercise's assumed starting state:

- The exercise names `EnumHelper.java`, but that file is absent from the source tree.
- `JsonDataStore.saveLoans` and `savePatrons` already use `stream().map(...).toList()`, rather than the described for-loops.

Do **not** invent an `EnumHelper` file or downgrade working Streams code just to perform the advertised refactoring. Check your checkout before proceeding. If your trainer supplies the exercise-specific starting state, use the conditional refactoring tasks below. Otherwise, complete the review/regression portion and report the unavailable transformations; that is **not equivalent to completing both original refactorings**.

## Establish behavior and investigate

1. Start from the [prepared Maven project](../setup/local-java-intellij.md). Record the source revision and run `mvn clean test`. Keep the actual baseline result.
2. Open `JsonDataStore.java` and the three status enums: `LoanReturnStatus`, `LoanExtensionStatus`, and `MembershipRenewalStatus`.
3. In **Copilot Chat > Ask**, attach those files using [GitHub's documented JetBrains file references](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains). Ask which duplication or branching is present **in this checkout**, and which transformations in the original exercise are already done or unavailable.
4. Verify each claim in the actual source. Ask how message lookups and persistence-only entity copies behave. Identify the existing test coverage and any observable gaps.

## Conditional task: enum-description dispatch

Only perform this section if your supplied starter actually contains the described helper/dispatch chain.

1. Reference the helper, all affected enums, and its callers. Ask Copilot to explain the current description behavior and compare a shared message interface with a map-based dispatch.
2. Confirm whether each enum already exposes `getMessage`, and whether a shared interface already exists. Agree on null/unknown-type behavior based on actual callers; do not accidentally change it.
3. In **Agent** mode, request the smallest refactoring that removes the redundant dispatch while preserving callers and message values. The shared `DescribedEnum` interface described upstream is one candidate, not an instruction to create an unnecessary abstraction.
4. Review all affected files and run tests, including checks for every affected enum value. [GitHub's JetBrains Agent guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains) documents proposed edits and command approvals.

If the helper is absent, mark this task **unavailable for this starter**, not passed.

## Conditional task: persistence refactoring

1. Ask Copilot to explain `saveLoans` and `savePatrons` using the real code. Confirm that persistence copies contain only the intended scalar fields and do not serialize populated navigation-object graphs.
2. If a supplied starter uses for-loops, request a focused Streams refactoring in Agent mode, preserving copied fields, ordering, serialization, and error behavior. Do not assume Streams are faster or that `toList()` has the same mutability as every existing list.
3. If Streams are already present, review them instead. There is no loop-to-Stream transformation left to apply; add relevant regression coverage only where it meaningfully tests the existing behavior.
4. Review any generated tests to ensure they use a test-owned temporary data directory for writes, not the shared fixtures. Compare saved JSON structure and values, not formatting alone.

## Verify and report

1. Run `mvn clean test`; the [IntelliJ Maven/JUnit runner](https://www.jetbrains.com/help/idea/work-with-tests-in-maven.html) is an alternative for focused tests.
2. Run `mvn exec:java` from the application directory and exercise a library flow. Note any sample-data changes; do not reset unrelated work.
3. In Ask mode, attach the diffs and tests and request a review of correctness, maintainability, and behavior preservation. Verify the response rather than treating it as proof.
4. Record which transformations were performed, already present, or unavailable, together with actual test results.

## Completion checkpoint

With an appropriate starter, both justified refactorings preserve behavior and pass relevant tests. With the inspected current starter, report **review/regression work completed, original enum task unavailable, Streams transformation already present**. Request a suitable starter from your trainer if full original-lab completion is required.
