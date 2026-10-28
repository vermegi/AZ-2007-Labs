# IntelliJ 02 - Analyze and document Java code

[Previous: interface](01-settings-and-interface.md) | [Java track](../tracks/java.md) | [Next: develop features](03-develop-features.md)

**Not battle tested.** Adapted from [Java exercise 02](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_02_analyze_document_code_java.md); see [sources and attribution](SOURCES.md). Goal: understand the library app, verify its behavior, and produce accurate project documentation.

## Inspect the application with Copilot

1. Start from the [prepared IntelliJ Maven project](../setup/local-java-intellij.md). Run `mvn clean test` from the directory containing the application's `pom.xml`. Resolve a failing baseline before treating generated changes as successful.
2. Open **Copilot Chat** in **Ask** mode. Following [GitHub's JetBrains file-reference workflow](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains), reference `App.java` and representative domain, service, repository, and console files.
3. Ask for a project overview that identifies which classes implement each responsibility. Check the named classes and methods in the IDE. If the response lacks context, attach the relevant files and ask again; do not assume merely mentioning a filename attaches it.
4. Reference `JsonDataStore.java`, `JsonLoanRepository.java`, and `JsonPatronRepository.java`. Ask how JSON records are loaded, linked by IDs, and saved. Confirm the explanation of `ensureDataLoaded`, `saveLoans`, and `savePatrons` against the source.
5. Ask how `App.java` initializes the app and how a selected service method uses the repositories. Inspect **References** and compare the answer with the actual call sites.

No `#codebase`, `@github`, `/explain`, or fixed model name is needed. This adaptation uses natural-language prompts and explicit file context; slash commands should be used only if your plugin documents and exposes them.

## Verify the explanation by running the app

1. From `AccelerateDevGHCopilot` in the [IntelliJ Terminal](https://www.jetbrains.com/help/idea/terminal-emulator.html), run:

   ```text
   mvn exec:java
   ```

2. Exercise a patron search and inspect a loan through the app's displayed options. Compare the visible status with the corresponding local JSON records. Use the return-book scenario in the [original exercise](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_02_analyze_document_code_java.md#build-and-run-the-application) if you need the exact scenario.
3. Exit using the app's displayed quit option. Returning a book changes sample data; note those changes so later tests are not interpreted against an assumed pristine dataset.

The program needs the working directory containing `data`, not an arbitrary IDE terminal directory.

## Write and verify the README

1. In Ask mode, request Markdown documentation for the library app: purpose, project structure, key types, setup/usage, and the actual license. Attach the application and build files needed to support those claims.
2. Save your reviewed response as `README.md` in the **application project**, not this guidance repository. GitHub documents response copy/insert actions in its [JetBrains chat guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains); manual copy and editing is an explicit alternative to generated file edits.
3. Check every claimed command, directory, entry point, dependency, and license against the project. Remove invented features and do not describe the exercise's incomplete book-search method as implemented.
4. Re-run any usage commands you describe and retain the actual outputs when reporting a failure.

## Completion checkpoint

You have a source-verified architectural explanation, observed application behavior, and a reviewed README for the library project. The upstream publishing question can be discussed in ordinary Chat; actual repository publication should follow [JetBrains Git documentation](https://www.jetbrains.com/help/idea/set-up-a-git-repository.html), not an assumed `@github` integration.
