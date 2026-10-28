# IntelliJ 01 - Settings and interface

[Setup](../setup/local-java-intellij.md) | [Java track](../tracks/java.md) | [Next: analyze and document](02-analyze-and-document.md)

**Not battle tested.** Adapted from the [Java exercise 01](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_01_examine_settings_interface.md); [attribution and boundaries](SOURCES.md) apply. The objective is to distinguish explanations, edits, and inline completions in **GitHub Copilot for IntelliJ**, not to reproduce VS Code's settings editor.

## Review Copilot controls

1. Complete [IntelliJ preparation](../setup/local-java-intellij.md). Open the Java application's `App.java`.
2. Use the Copilot status icon to inspect completion availability. Review the plugin's configuration through [GitHub's JetBrains configuration instructions](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/set-up-copilot/configure-in-ide?tool=jetbrains). Record the original values before changing any setting, and restore temporary changes afterward.
3. Check that the signed-in account has Copilot access and that required features are not blocked by policy. Do not look for VS Code settings such as `github.copilot.enable`, `inlineChat.askInChat`, or `chat.permissions.default` in IntelliJ.

## Compare Ask and Agent

[GitHub documents JetBrains modes, chat, and file references here](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains).

1. Open the **Copilot Chat** tool window using its icon, select **Ask**, and reference `App.java` by dragging it into the prompt box. Alternatively, right-click the file and use **GitHub Copilot > Reference File in Chat**.
2. Ask in your own words how startup connects the data store, repositories, services, and console. Compare the response with the file and inspect **References**. An explanation should not require code changes.
3. Open `LoanService.java`, select `extendLoan`, and ask for an explanation of its overdue-date check. Ask for one readability improvement without applying it.
4. Select **Agent** using the control available in your plugin version. Ask it to add only one short explanatory comment at that check. Review the actual diff and any proposed commands before approving them. [GitHub's JetBrains Agent guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains) documents edit review and command approval. Do not enable blanket approvals for the exercise.
5. Remove only the comment you just added if you want to leave the starter unchanged. Do not reset unrelated work. If Agent is unavailable because of policy or version compatibility, record that limitation: Ask-only use is not equivalent to completing the Agent task.

## Try completions and focused questions

1. In a Java file, type a small, meaningful partial statement or descriptive comment and observe any inline code suggestion. Review it before accepting; discard the temporary experiment afterward. Use the accept/dismiss controls documented for your OS/keymap in [GitHub's JetBrains code-suggestion guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/copilot-for-common-tasks/get-ide-code-suggestions?tool=jetbrains).
2. Select a method and ask Copilot Chat to explain it, then ask for a code-quality assessment. This preserves the source exercise's explanation/review objectives without assuming a specific VS Code Smart Actions menu.
3. Optional: use **GitHub Copilot > Copilot: Inline Chat** from the editor context menu if available, following the [JetBrains section of GitHub's chat guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains). This is not VS Code's `Ctrl+I` workflow.

## Completion checkpoint and deliberate differences

You can identify your signed-in Copilot account, distinguish Ask from Agent, attach a real file, verify an explanation, and review a proposed edit and completion.

The source's **Quick Chat**, VS Code settings keys, specific Keep/Undo UI, and Smart Actions menu labels are not transplanted. Next edit suggestions are not a required task: consult the [current feature matrix](https://docs.github.com/en/copilot/reference/copilot-feature-matrix) for JetBrains availability/preview status rather than expecting VS Code parity. Restore only settings and edits changed during this exercise.
