# Java exercise track

[Choose an environment](../../README.md#choose-your-route)

**Experimental community adaptation.** Use the [Java source repository](https://github.com/mkennten/mslearn-github-copilot-dev-java), not the Microsoft C#/Python repository or this guidance repository, for the Maven project.

## Choose the instructions for your environment

- [Local VS Code](../setup/local-java-vscode.md): Java 21 and Maven 3.9+ on your computer.
- [GitHub Codespaces](../setup/codespaces-java.md): upstream Java container hosted by GitHub.
- [Local Dev Containers](../setup/devcontainers-java.md): the same container with VS Code and local Docker.
- [Local IntelliJ IDEA](../setup/local-java-intellij.md): separate adaptations, **not battle tested**.

The shared project for 01-05 is the upstream `AccelerateDevGHCopilot` Maven application. Unlike the official learn path's C# and Python tracks, the Java sources reuse this single project, so review existing changes before continuing. Exercise 06 creates a separate web prototype. Use the dependencies already declared in the project's `pom.xml`; upstream prose and dependency versions can drift.

## Ordered exercises

| Order | VS Code / Codespaces / Dev Containers: original instructions | IntelliJ: local adaptation |
| --- | --- | --- |
| 01 | [Settings and interface](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_01_examine_settings_interface.md) | [Settings and interface](../intellij/01-settings-and-interface.md) |
| 02 | [Analyze and document Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_02_analyze_document_code_java.md) | [Analyze and document](../intellij/02-analyze-and-document.md) |
| 03 | [Develop Java features](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_03_develop_code_features_java.md) | [Develop features](../intellij/03-develop-features.md) |
| 04 | [Develop unit tests: JUnit](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_04_develop_unit_tests_junit.md) | [Unit tests](../intellij/04-unit-tests.md) |
| 05 | [Refactor Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_05_refactor_improve_existing_code_java.md) | [Refactoring](../intellij/05-refactoring.md) |
| 06 | [Vibe-code a shopping prototype](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_06_vibe_coding_prototype_ecommerce_app.md) | [Vibe coding](../intellij/06-vibe-coding.md) |

## Boundaries and caveats

- 06 is HTML/CSS/JavaScript, not a Java application exercise; Java's simple web server can serve the static files.
- The Java adaptation ends at 06. Official learn path exercises 07-16 are C#/.NET-specific, with no supplied Java variants. Do not follow their C# prerequisites.
- Copilot features depend on IDE/plugin version, plan, and organization policy. Do not transfer VS Code commands, settings names, or shortcuts to IntelliJ.
- The inspected Java starter differs from parts of the upstream prose: `GetLoanTest.java` is absent, `EnumHelper.java` is absent, and the persistence methods already use Streams. The [IntelliJ source notes](../intellij/SOURCES.md#feature-and-starter-boundaries) explain the adaptations; VS Code/container learners should also check their actual starter and ask their trainer if exercise 05 needs an earlier starting state.
- Container configuration has been inspected, but a successful build or end-to-end walkthrough has **not** been verified here. For browser previews in a container, follow official port-forwarding instructions linked from the option page; a container's `localhost` is not automatically your browser's host.
- [IntelliJ feature boundaries and source attribution](../intellij/SOURCES.md) distinguish documented support from actual testing.
