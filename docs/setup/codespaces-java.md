# GitHub Codespaces: Java

[All options](../../README.md#choose-your-route) | [Java track](../tracks/java.md) | [Local container alternative](devcontainers-java.md)

**Java-only, experimental labs.** This option hosts the upstream Java development container on GitHub; you do not need a local Java/Maven or Docker installation.

## Prerequisite reminder and original setup links

- Own GitHub account with [Copilot access](https://docs.github.com/en/copilot/get-started/plans), permission to create a Codespace, and available Codespaces usage/budget.
- Browser and network access to GitHub Codespaces.
- [Original Java Codespaces setup](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_00_configure_lab_environment.md#open-the-repository-in-github-codespaces).
- [Original Copilot and workspace checks](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_00_configure_lab_environment.md#verify-github-copilot-access).
- [Official Codespaces billing information](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces), [stopping a Codespace](https://docs.github.com/en/codespaces/developing-in-a-codespace/stopping-and-starting-a-codespace), and [deleting a Codespace](https://docs.github.com/en/codespaces/developing-in-a-codespace/deleting-a-codespace).

The project is in the [Java source repository](https://github.com/mkennten/mslearn-github-copilot-dev-java), not this guide. Its [upstream dev-container configuration](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/.devcontainer/devcontainer.json) supplies Java 21, Maven, and VS Code Java extensions. For 01-05, the Maven project is `AccelerateDevGHCopilot`.

## Lab links in order

1. [01 - Settings and interface](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_01_examine_settings_interface.md)
2. [02 - Analyze and document Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_02_analyze_document_code_java.md)
3. [03 - Develop Java features](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_03_develop_code_features_java.md)
4. [04 - Unit tests: JUnit](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_04_develop_unit_tests_junit.md)
5. [05 - Refactor Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_05_refactor_improve_existing_code_java.md)
6. [06 - Vibe-code a web prototype](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_06_vibe_coding_prototype_ecommerce_app.md)

## Container-specific caveats

- 06 is a separate HTML/CSS/JavaScript prototype. Use [official Codespaces port-forwarding guidance](https://docs.github.com/en/codespaces/developing-in-a-codespace/forwarding-ports-in-your-codespace) for its preview; a raw container `localhost` URL is not the browser-facing URL.
- Stopping compute and deleting stored environments are different; storage may remain billable after stopping. Follow the billing/cleanup links above.
- The configuration has been inspected, **not built or tested end to end here**. The Java instructions do not cover 07-16.
