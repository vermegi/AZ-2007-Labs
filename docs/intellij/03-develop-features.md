# IntelliJ 03 - Develop Java features

[Previous: analysis](02-analyze-and-document.md) | [Java track](../tracks/java.md) | [Next: unit tests](04-unit-tests.md)

**Not battle tested.** Adapted from [Java exercise 03](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_03_develop_code_features_java.md); see [sources and attribution](SOURCES.md). Goal: implement book search, test it, and review the change through a branch/pull request.

## Establish the baseline and branch

1. Use the [prepared Maven project](../setup/local-java-intellij.md). Before edits, run `mvn clean test` from `AccelerateDevGHCopilot` and record the result.
2. Confirm you have a repository you can push to, such as your own fork. Use [JetBrains' documented branch workflow](https://www.jetbrains.com/help/idea/manage-branches.html) to create a `book-search` feature branch. Do not assume write access to the community source repository.
3. Inspect `BookRepository.java`, `JsonBookRepository.java`, `JsonDataStore.java`, and the `Book`/`Author` types. The inspected starter's `searchBooks` throws `UnsupportedOperationException`; if your checkout differs, first identify the remaining task.

## Investigate, implement, and review

1. In **Copilot Chat > Ask**, attach the relevant files using the [documented JetBrains file-reference workflow](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains). Ask how title/author data can be queried through the **actual public API**.
2. Agree on the method's contract before generation: case-insensitive title or author-name matching, appropriate behavior for no matches and null/empty input, and null-safe handling of incomplete author data. Treat edge-case behavior as an explicit decision to encode in tests, not a guessed requirement.
3. Switch to **Agent**, following [GitHub's JetBrains Agent documentation](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains), and request an implementation of `searchBooks` consistent with that contract. Ask it to load data before querying, use existing domain relationships, and keep the change focused.
4. Review the proposed diff before proceeding. If the data store exposes no suitable book-query API, have Copilot explain and propose the smallest necessary change rather than inventing a nonexistent accessor or accessing private fields.
5. Use Ask with the changed files attached to review locale/case behavior, missing authors, empty input, and no-match results. Apply only changes you understand.

You may use the plugin's documented inline-chat action for a single-method edit, but this rewrite does not assume VS Code's inline-chat shortcut or its accept UI.

## Generate and run tests

1. In Agent mode, request a `JsonBookRepositoryTest` test class covering title search, author search, case variation, no results, and the chosen null/empty-input behavior. Include current test files and `pom.xml` as context.
2. Require the existing JUnit/Mockito setup and package conventions. Do not ask for a particular JUnit major version or Mockito extension that the project has not declared; the current dependency file takes precedence over older prose.
3. Review both assertions and fixture data. Check that title and author tests would fail for a broken implementation, rather than merely asserting a non-null result.
4. Run `mvn test` from the Maven project directory. Alternatively, use the [documented IntelliJ Maven/JUnit runner](https://www.jetbrains.com/help/idea/work-with-tests-in-maven.html). Add actual failure output to a follow-up Ask request rather than accepting a model's assertion that tests passed.
5. Run `mvn exec:java` for a basic regression check of the console app. A successful unrelated loan-return flow does **not** prove search correctness; the dedicated search tests provide that evidence.

## Commit and pull request

Use the [JetBrains commit workflow](https://www.jetbrains.com/help/idea/commit-and-push-changes.html) and [GitHub pull-request workflow](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

1. Review the changed files, including unintended sample-data edits from earlier runs. Commit only the intended feature/tests to your feature branch.
2. Ask Copilot for a commit-message draft and a PR description summarizing behavior, changed files, and actual test results. Review them; no sparkle-button integration is assumed.
3. Push to your own training repository and create a PR against **its** default branch. For a fork, check the base repository explicitly so you do not accidentally submit a training PR to the upstream maintainer.
4. Merge your own training PR if permitted, then synchronize your local default branch before the next exercise.

## Completion checkpoint

The search contract is implemented, relevant new and existing tests pass, and your own repository has a reviewed feature change. If Agent is unavailable, you may manually apply Ask-generated code as a labelled fallback, but you have **not** completed the Agent-specific part of the exercise.
