# Local VS Code Dev Containers + Docker: Java

[All options](../../README.md#choose-your-route) | [Java track](../tracks/java.md) | [Hosted Codespaces alternative](codespaces-java.md)

**Java-only, experimental labs.** Use the same upstream development-container configuration as Codespaces, but run it on your computer. This is **not a local Codespace**.

## Prerequisite reminder and original setup links

- Own GitHub account and [Copilot access](https://docs.github.com/en/copilot/get-started/plans).
- Local VS Code with the **Dev Containers** extension, a running Docker installation that supports **Linux containers**, sufficient local memory/disk, and network access for image/dependency downloads.
- Git for the local-checkout workflow, or the prerequisites for the clone-in-container workflow described in the official documentation.
- [Official VS Code Dev Containers requirements and setup](https://code.visualstudio.com/docs/devcontainers/containers) and [tutorial](https://code.visualstudio.com/docs/devcontainers/tutorial).
- [Docker Desktop requirements and installation](https://docs.docker.com/desktop/) and [subscription/license considerations](https://docs.docker.com/subscription/desktop-license/). Windows users should check the documented WSL 2/virtualization requirements.

The workspace is the [upstream Java repository](https://github.com/mkennten/mslearn-github-copilot-dev-java). Its existing [dev-container configuration](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/.devcontainer/devcontainer.json) supplies **Java 21, Maven, and Java extensions inside the container**; they need not be installed on the host. This guidance repository does not contain a container configuration or sample application.

Use the official VS Code instructions for opening an existing repository in its container, then the upstream [Copilot/workspace readiness checks](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_00_configure_lab_environment.md#verify-github-copilot-access). The source describes local and Codespaces environments rather than a separate Dev Containers route; container-opening procedures therefore come from VS Code documentation.

## Lab links in order

1. [01 - Settings and interface](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_01_examine_settings_interface.md)
2. [02 - Analyze and document Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_02_analyze_document_code_java.md)
3. [03 - Develop Java features](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_03_develop_code_features_java.md)
4. [04 - Unit tests: JUnit](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_04_develop_unit_tests_junit.md)
5. [05 - Refactor Java code](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_05_refactor_improve_existing_code_java.md)
6. [06 - Vibe-code a web prototype](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_06_vibe_coding_prototype_ecommerce_app.md)

## Container-specific caveats

- For 01-05, `AccelerateDevGHCopilot` is the Maven project **inside the container**. The Linux container's shell/path syntax differs from a Windows host's shell.
- 06 is HTML/CSS/JavaScript. Follow [VS Code container port-forwarding guidance](https://code.visualstudio.com/docs/devcontainers/containers#_forwarding-or-publishing-a-port) for its browser preview rather than assuming that a container loopback URL is host-accessible.
- Local Docker uses your computer's resources and does not consume Codespaces compute/storage allowance. Docker licensing and Copilot usage limits are separate considerations.
- Stop unused containers using [Docker's container-management guidance](https://docs.docker.com/desktop/use-desktop/container/); review retained images/volumes separately. Do not remove volumes that contain work you want to keep.
- The upstream configuration has been inspected, **not built or walked through here**. No Java exercises 07-16 are supplied.
