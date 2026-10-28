# IntelliJ 06 - Vibe-code a web prototype

[Previous: refactoring](05-refactoring.md) | [Java track](../tracks/java.md) | [All options](../../README.md#choose-your-route)

**Not battle tested.** Adapted from [Java-source exercise 06](https://github.com/mkennten/mslearn-github-copilot-dev-java/blob/main/Instructions/Labs/LAB_AK_06_vibe_coding_prototype_ecommerce_app.md); see [sources and attribution](SOURCES.md). This is **HTML/CSS/JavaScript**, not a Java backend exercise. Use GitHub Copilot to turn requirements into a prototype and iteratively validate it.

## Scope and IntelliJ differences

- Use the official GitHub Copilot plugin's **Ask** and **Agent** modes, not JetBrains AI Assistant/Junie. [GitHub documents the JetBrains workflows](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains).
- This route does not require IntelliJ's integrated JavaScript debugger, web preview, framework generators, or paid web-development features. The generated static files are exercised in an external browser.
- Instead of VS Code's multi-root workspace, use a standalone prototype project with its own repository. This deliberately isolates its files and Copilot instructions from the Java library project.
- Do not add a backend, real authentication, payment processing, or database integration. A static preview server is not an application backend.

## Define requirements and wireframes

1. Create a separate `VibeCoding-PrototypeApp` folder outside the library checkout and open it as an IntelliJ project. Use [JetBrains' project guidance](https://www.jetbrains.com/help/idea/creating-and-managing-projects.html) and [Git repository setup](https://www.jetbrains.com/help/idea/set-up-a-git-repository.html) so this folder is the prototype's own repository root. Do not create the prototype in this guidance repository.
2. In **Ask**, describe a small shopping prototype with product listing, product details, cart, checkout, and navigation. Request a PRD outline covering purpose, audience, use cases, sample data, constraints, and measurable acceptance criteria.
3. Refine the requirements: ten fruit products with names, descriptions, units/prices, and representative icons; selectable quantities; editable/removable cart items; correct line/total prices; and a simulated order confirmation. Require the navigation to remain on the left and initially collapse to abbreviated labels below a 300-pixel viewport width.
4. Explicitly exclude real transactions and backend services. Ask Copilot to resolve ambiguities before generating code.
5. Switch to **Agent** and request `VibeCodingPRD.md` in the project root and one text wireframe per page plus navigation. Review the generated files for consistency. [GitHub's JetBrains Agent guide](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/use-copilot-agents/use-agent-mode?tool=jetbrains) documents file edits and command approval.

## Generate the first prototype

1. Create an empty `ShoppingApp` folder within the prototype project, or ask Agent to create it. Reference the PRD and wireframes using [JetBrains file references](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/chat-with-copilot/chat-in-ide?tool=jetbrains); do not assume selecting a directory attaches its contents.
2. Ask Agent to implement the agreed prototype in `ShoppingApp` using only HTML, CSS, and JavaScript. Ask for readable code and no external build tool requirement, backend, credentials, or real checkout processing.
3. Review file placement, code changes, and commands before approving them. Expect an HTML entry point, stylesheet, and JavaScript implementation, but verify the actual filenames and references rather than treating model output as fixed.
4. In the **prototype repository root**, create `.github/copilot-instructions.md` with the agreed project constraints and measurable requirements, following [GitHub's official JetBrains custom-instructions documentation](https://docs.github.com/en/copilot/how-tos/copilot-in-your-ide/customize-copilot/configure-custom-instructions/add-repository-instructions-in-your-ide?tool=jetbrains). This is the lab artifact, not an instruction file to add to this guidance repository.
5. Check the [feature matrix](https://docs.github.com/en/copilot/reference/copilot-feature-matrix) and your installed plugin's support. If custom instructions are unavailable or their use cannot be confirmed, explicitly attach the PRD/wireframes on each request as a **manual fallback**; do not claim automatic instruction loading was demonstrated. A model repeating the requirements is not proof of loading.

## Serve and test in a browser

1. Open the [IntelliJ Terminal](https://www.jetbrains.com/help/idea/terminal-emulator.html) with the working directory set to **ShoppingApp**, the folder containing the generated HTML entry point. Do not use the upstream example's absolute `/ShoppingApp` path on your machine.
2. With JDK 21's `jwebserver` available on the shell path, run:

   ```text
   jwebserver -b 127.0.0.1 -p 5500
   ```

   [Oracle's JDK 21 documentation](https://docs.oracle.com/en/java/javase/21/docs/specs/man/jwebserver.html) defines the tool, directory, bind-address, and port options. If the command is missing, verify that the terminal is using a full JDK and its `bin` directory. Do not substitute an invented IntelliJ server menu.
3. Open `http://127.0.0.1:5500` in your external browser, using the actual entry filename if it is not `index.html`. Keep the server bound to loopback; do not expose this training prototype publicly.
4. Verify product count/details, quantity selection, cart updates/removal, line prices, total price, simulated order confirmation, and navigation. Include empty-cart and repeated-add cases. Record observable failures.
5. Check different viewport sizes. A desktop window may not shrink below 300 pixels; use a browser's documented responsive-testing tools if needed, or record that the initial breakpoint could not be exercised. Do not mark an unobserved behavior as tested.

This procedure is for **native local IntelliJ**. Container preview/forwarding belongs to the separate Codespaces/Dev Containers routes.

## Refine against measurable requirements

1. Give Agent the observed failures and attached requirements. Request a change from the original 300-pixel collapse threshold to **below 600 pixels**, retaining left-side navigation. Update the PRD and, where supported, the repository instructions.
2. Test the behavior at viewport widths **599, 600, and 601 pixels**: under the agreed "below 600" contract, only 599 should use collapsed navigation. Check the viewport width, not the outer window width.
3. Request an icon per navigation destination, centered horizontally when collapsed. Review and verify that the navigation still works in both states.
4. Ask Copilot to compare the implementation against the PRD and wireframes. Select at least three useful refinements, such as in-app notifications, a simulated order thank-you state, and a cart-count badge. Define how you will verify each one, then request the changes and test them.
5. Re-run the earlier use cases after each refinement. Inspect browser errors and the actual diff; agent assurances alone are not test results.

## Completion checkpoint and cleanup

You have a reviewed PRD, wireframes, static prototype, and recorded browser checks before/after refinement. Reopen the project using IntelliJ's project mechanism; no VS Code `.code-workspace` file is needed.

Stop the preview server with **Ctrl+C** in the terminal that runs it, as documented by Oracle. Keep or archive your own prototype as desired, and preserve work before removing any lab artifacts.
