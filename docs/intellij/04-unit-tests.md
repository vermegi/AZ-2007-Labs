# IntelliJ 04 - Develop unit tests

[Previous: features](03-develop-features.md) | [Java track](../tracks/java.md) | [Next: refactoring](05-refactoring.md)

**Not battle tested.** Adapted from [Java exercise 04](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_04_develop_unit_tests_junit.md); see [sources and attribution](SOURCES.md). Goal: understand service-test conventions and add repository tests for `JsonLoanRepository.getLoan`.

## Understand the test structure

1. Start with the [prepared Maven project](../setup/local-java-intellij.md) and a passing `mvn clean test` baseline.
2. Open `LoanServiceTest.java`, `PatronServiceTest.java`, `LoanFactory.java`, and `PatronFactory.java` in the project's test source tree. Inspect `pom.xml` for the actual JUnit and Mockito dependencies; do not replace them just because the upstream prose mentions another version.
3. In **Copilot Chat > Ask**, reference these files with the [documented JetBrains context controls](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains). Ask how fixtures, mocks, and arrange/act/assert are used, and which conventions should carry over to repository tests.
4. Add `JsonLoanRepository.java`, `JsonDataStore.java`, and `Loans.json`. Ask why a repository test backed by JSON differs from a service unit test with mocked repositories. Verify the explanation against the code.

## Add the repository test class

**Starter correction:** the inspected Java source does not include the `GetLoanTest.java` stub described in the original exercise. Do not spend time searching for a file that is absent.

1. Use **Agent** as documented in [GitHub's JetBrains Agent guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains). Ask it to create `GetLoanTest.java` in the test package corresponding to `repository.json`, or extend it if your checkout already has it.
2. Request setup for a real `JsonLoanRepository` backed by `JsonDataStore` and the existing `data/Json` fixtures. Use the actual constructors from the referenced code and existing JUnit lifecycle conventions.
3. Have Copilot explain whether any mock is actually needed. A mock that is never used does not strengthen this real-data repository test. This intentionally avoids reproducing the source exercise's redundant mock field.
4. Review the package, imports, fixture path, and setup before accepting. A test reading repository JSON is fixture-backed integration-style coverage; do not confuse it with an isolated service unit test.

## Test found and missing IDs

1. Identify an ID that **actually exists** in the local `Loans.json`. Ask Agent to test that `getLoan` returns the corresponding loan and preserves its ID.
2. Choose an ID verified to be absent in that file. Ask for a test of the actual not-found contract. The inspected implementation returns `null`; confirm your checkout before asserting that behavior. Do not assume `99999` is forever unused.
3. Ask for descriptive JUnit `@DisplayName` annotations and clear assertions, using the project's current dependencies. Verify both tests would detect wrong behavior.
4. Ensure the tests do not save or mutate the shared sample JSON. If isolation is needed, request test-owned copies rather than overwriting the checked-in fixtures.

## Run and diagnose

[JetBrains documents both JUnit and Maven test execution](https://www.jetbrains.com/help/idea/work-with-tests-in-maven.html).

1. Run the new test through the IntelliJ gutter run action, or through Maven's `test` lifecycle goal.
2. Run `mvn test` from `AccelerateDevGHCopilot` to include the full suite. Check the reported test counts so an undiscovered class is not mistaken for passing tests.
3. If a data-path failure occurs, verify the working directory and fixture existence. For an IDE test configuration, ensure its working directory is the application folder containing `data`. Ask Copilot with the full error and relevant files if needed.
4. Review that service tests still pass and that the new tests do not depend on execution order or silently modified data.

## Completion checkpoint

You can explain the testing approach and demonstrate discovered, passing found-ID and missing-ID repository tests. A generated test file alone is not completion. No VS Code Test Explorer, `#codebase`, or undocumented test-generation menu is assumed.
