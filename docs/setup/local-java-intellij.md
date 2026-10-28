# Your computer + IntelliJ IDEA: Java

[All options](../../README.md#choose-your-route) | [Java track](../tracks/java.md) | [Sources and feature boundaries](../intellij/SOURCES.md)

**Not battle tested.** This is an original IntelliJ adaptation of the community Java labs, not official Microsoft or JetBrains training. Procedures are grounded in official documentation, but no IntelliJ/plugin version has been tested here. Exercise 05 is **partially applicable to the inspected starter**; see its checkpoint before attempting it.

## Prerequisites

- Your own GitHub account and [Copilot access](https://docs.github.com/en/copilot/get-started/plans), subject to organization policies.
- IntelliJ IDEA compatible with the [official GitHub Copilot plugin](https://plugins.jetbrains.com/plugin/17718-github-copilot/versions). Use the latest compatible stable IDE/plugin; do not assume all versions expose the same controls.
- Git 2.48+, JDK 21, Maven 3.9+, and a browser. Use the dependencies declared by the upstream Maven project rather than changing them to match older lab prose.
- The **GitHub Copilot plugin**, not JetBrains AI Assistant or Junie.

## IntelliJ-specific preparation

These are part of the IntelliJ adaptation exception; original VS Code setup steps are not reproduced.

1. Follow [GitHub's official JetBrains installation and sign-in instructions](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/set-up-copilot/install-copilot-extension?tool=jetbrains) to install the GitHub Copilot plugin through the IDE's Plugins Marketplace and sign in to your own GitHub account.
2. Obtain a local checkout of the [Java sample repository](https://github.com/mkennten/mslearn-github-copilot-dev-java), using [JetBrains' documented Git clone workflow](https://www.jetbrains.com/help/idea/set-up-a-git-repository.html). For exercise 03's push/pull-request tasks, use a fork you own or another training repository where you have write permission. Do not expect write access to the original repository; see [GitHub's fork guidance](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo).
3. Open/sync the Maven project defined by `AccelerateDevGHCopilot/pom.xml`, using [IntelliJ's Maven integration](https://www.jetbrains.com/help/idea/maven-support.html). Select JDK 21 for the project and Maven execution as documented there. Opening only this guidance repository will not provide the application.
4. Open the IDE's [Terminal tool window](https://www.jetbrains.com/help/idea/terminal-emulator.html). With its current directory set to `AccelerateDevGHCopilot` (the folder containing `pom.xml` and `data`), verify the toolchain and baseline:

   ```text
   java -version
   mvn -version
   mvn clean test
   ```

   Both the shell and Maven must report the intended JDK. A successful baseline means the existing suite passes; it does not mean deliberately incomplete exercise code is implemented. If this fails, retain the actual error and resolve the documented prerequisite or ask your trainer before proceeding. Do not ignore failures.
5. Open **Copilot Chat** using the plugin's chat icon. Select **Ask** for an initial explanation, reference `App.java`, and confirm the answer identifies actual code. [GitHub's JetBrains chat documentation](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains) documents the chat icon, mode selection, file references, and the response's **References** link.

Record your IDE, plugin, JDK, and Maven versions and any policy limitations when reporting a problem. There is deliberately no claimed tested version combination here.

## Lab links in order

1. [01 - Settings and interface](../intellij/01-settings-and-interface.md)
2. [02 - Analyze and document](../intellij/02-analyze-and-document.md)
3. [03 - Develop features](../intellij/03-develop-features.md)
4. [04 - Unit tests](../intellij/04-unit-tests.md)
5. [05 - Refactoring](../intellij/05-refactoring.md) - starter mismatch: see the applicability checkpoint.
6. [06 - Vibe-code a web prototype](../intellij/06-vibe-coding.md)

Each adaptation links its original Java exercise. Microsoft exercises 07-16 are C#/.NET-specific and are omitted. These adaptations use documented JetBrains Chat/Agent/file-reference workflows instead of assuming VS Code shortcuts, `#codebase`, `@github`, Quick Chat, or Keep/Undo controls exist unchanged.
