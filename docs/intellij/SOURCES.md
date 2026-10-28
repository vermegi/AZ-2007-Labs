# IntelliJ adaptations: sources and boundaries

[All options](../../README.md#choose-your-route) | [IntelliJ setup](../setup/local-java-intellij.md) | [Java track](../tracks/java.md)

## Status and source revisions

These are locally authored adaptations, **not battle tested**, not official IntelliJ training, and not a promise of feature parity with VS Code. No tested IntelliJ/plugin version combination is claimed. Official documentation and public source code were inspected on **2026-10-28**; a complete IDE walkthrough has not been performed.

The original learning tasks come from the community [Java lab repository](https://github.com/mkennten/mslearn-github-copilot-dev-java), itself a Java-focused adaptation of [Microsoft's exercises](https://github.com/MicrosoftLearning/mslearn-github-copilot-dev). The original steps remain upstream; only these IntelliJ adaptations are written here.

Audit references:

- [Java source revision d1973fb](https://github.com/mkennten/mslearn-github-copilot-dev-java/tree/d1973fb8605634150a17facef7b819d3d567c4e7).
- [Microsoft source revision 21e1741](https://github.com/MicrosoftLearning/mslearn-github-copilot-dev/tree/21e174105fab6af9aec18f401ee97fe13a9fcae2).

Learner links elsewhere use `main` for current instructions. If the source changes, compare it with these audit references rather than assuming the same starter state.

## Official documentation used

| Topic | Official reference |
| --- | --- |
| Plugin compatibility, installation, sign-in | [GitHub: install Copilot, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/set-up-copilot/install-copilot-extension?tool=jetbrains) and [plugin versions](https://plugins.jetbrains.com/plugin/17718-github-copilot/versions) |
| Enablement and configuration | [GitHub: configure Copilot, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/set-up-copilot/configure-in-ide?tool=jetbrains) |
| Ask/edit/agent selection, file references, chat, inline chat | [GitHub: chat in IDE, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains) |
| Agent edits and command approvals | [GitHub: Agent mode, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains) |
| Inline code suggestions | [GitHub: code suggestions, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/copilot-for-common-tasks/get-ide-code-suggestions?tool=jetbrains) |
| Repository custom instructions | [GitHub: repository instructions in your IDE, JetBrains section](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/customize-copilot/configure-custom-instructions/add-repository-instructions-in-your-ide?tool=jetbrains) |
| Availability and previews | [GitHub: Copilot feature matrix](https://docs.github.com/en/copilot/reference/copilot-feature-matrix) |
| Project model and Maven | [JetBrains: projects](https://www.jetbrains.com/help/idea/creating-and-managing-projects.html) and [Maven](https://www.jetbrains.com/help/idea/maven-support.html) |
| Terminal and tests | [JetBrains: terminal](https://www.jetbrains.com/help/idea/terminal-emulator.html) and [testing in Maven](https://www.jetbrains.com/help/idea/work-with-tests-in-maven.html) |
| Git workflows | [JetBrains: repository setup](https://www.jetbrains.com/help/idea/set-up-a-git-repository.html), [branches](https://www.jetbrains.com/help/idea/manage-branches.html), [commit/push](https://www.jetbrains.com/help/idea/commit-and-push-changes.html) |
| Forks and pull requests | [GitHub: fork a repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) and [create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) |
| Static preview server | [Oracle: JDK 21 jwebserver](https://docs.oracle.com/en/java/javase/21/docs/specs/man/jwebserver.html) |

Use the **JetBrains** tab/section of GitHub documentation: a fetched page may contain several IDE sections. Menu placement and keymaps can vary; if a documented capability is absent from your installation, check version/policy compatibility rather than trying VS Code commands.

## Feature and starter boundaries

- Chat, code completions, and Agent mode have official JetBrains documentation. Their presence does not establish exact parity with VS Code's controls.
- No dependency on VS Code Quick Chat, `#codebase`, `@github`, settings keys, Smart Actions labels, or Keep/Undo controls is introduced. Natural-language requests and explicitly referenced files are used instead.
- Inline chat is used only through the documented JetBrains action. Next edit suggestions are optional; custom instructions have an explicit manual-context fallback. Check current preview status and policy access.
- The adaptation does not substitute JetBrains AI Assistant or Junie for GitHub Copilot.
- The current [Maven dependency file](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/AccelerateDevGHCopilot/pom.xml) declares a newer JUnit version than the prose's JUnit 5 references. Use the project's declared dependencies and existing tests, not a hard-coded older version.
- The inspected tree has no `GetLoanTest.java` stub; [exercise 04](04-unit-tests.md) creates it when absent.
- The inspected tree has no `EnumHelper.java`; `saveLoans`/`savePatrons` already use Streams. [Exercise 05](05-refactoring.md) explicitly distinguishes review/regression work from unavailable or already-completed transformations. Do not claim full original-lab completion against that starter.
- Exercise 06 uses a standalone prototype repository instead of a VS Code multi-root workspace. This keeps project instructions separate from the Java library. Browser verification does not require IntelliJ's paid web tooling.
- Source sample projects can contain deliberately incomplete code. A passing baseline suite is not proof that every unfinished feature works.

## Attribution and upstream license

The original Java learning material is distributed under the [upstream MIT license](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/d1973fb8605634150a17facef7b819d3d567c4e7/LICENSE). The following notice is retained for the upstream material adapted in this directory; it does not relicense unrelated repository content or the linked official documentation.

```text
MIT License

Copyright (c) 2026 Microsoft

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
