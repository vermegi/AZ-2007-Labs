# C# exercise track

[Choose an environment](../../README.md#choose-your-route) | [Local C# option](../setup/local-csharp.md) | [Skillable option](../setup/skillable.md)

Use the [Microsoft source repository](https://github.com/MicrosoftLearning/mslearn-github-copilot-dev), **not this guidance repository**, for sample code. These links open the original published instructions; no exercise steps are reproduced here.

## Preparation

- [C# environment prerequisites and setup](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_00_configure_lab_environment.html).
- [Enable Copilot in VS Code](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_00_enable_github_copilot_in_visual_studio_code.html).
- Own GitHub account and sufficient [Copilot access](https://docs.github.com/en/copilot/get-started/plans). Free-plan limits or organization policies may affect completion.

## Ordered exercises

All 16 exercises below apply to this track. They do not all use the same project: follow each source exercise's project selection/import instructions.

| Order | Original exercise | Project or prerequisite reminder |
| --- | --- | --- |
| 01 | [Settings and interface](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_01_examine_settings_interface.html) | Shared VS Code introduction; choose the .NET option. |
| 02 | [Analyze and document code](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_02_analyze_document_code.html) | Library sample under `LabFiles/02-analyze-document-code`. |
| 03 | [Develop new features](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_03_develop_code_features.html) | Its own library starter under `LabFiles/03-develop-code-features`. |
| 04 | [Develop unit tests: xUnit](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_04_develop_unit_tests_xunit.html) | Use `LabFiles/04-develop-unit-tests-xunit`, not pytest. |
| 05 | [Refactor existing code](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_05_refactor_improve_existing_code.html) | Library starter under `LabFiles/05-refactor-improve-existing-code`. |
| 06 | [Vibe-code a shopping prototype](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_06_vibe_coding_prototype_ecommerce_app.html) | New HTML/CSS/JavaScript prototype; not the library app. |
| 07 | [Consolidate duplicate code](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_07_consolidate_duplicate_code.html) | Samples under `LabFiles/07-consolidate-duplicate-code`. |
| 08 | [Refactor large functions](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_08_refactor_large_functions.html) | Samples under `LabFiles/08-refactor-large-functions`. |
| 09 | [Simplify complex conditionals](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_09_simplify_complex_conditionals.html) | Loan approval and pricing samples under `LabFiles/09-simplify-complex-conditionals`. |
| 10 | [Implement performance profiling](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_10_implement_performance_profiling.html) | ContosoOnlineStore under `LabFiles/10-implement-performance-profiling`. |
| 11 | [Resolve GitHub issues](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_11_resolve_github_issues.html) | Separate ContosoShopEasy repository; follow the source import/issue setup. |
| 12 | [Resolve secret-scanning alerts](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_12_resolve_github_secret_scanning_alerts.html) | Separate ContosoOrderProcessor repository; verify repository permissions and scanning availability. Use only the lab's example data, never real credentials. |
| 13 | [Spec Kit: greenfield application](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_13_get-started-spec-driven-development.html) | New RSS-reader application. First follow [Spec Kit preparation](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_00_configure_github_dev_kit_lab.html). |
| 14 | [Spec Kit: implement a product feature](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_14_implement-spec-driven-development.html) | Separate ContosoDashboard application; same Spec Kit preparation. |
| 15 | [Instructions and custom agents](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_15_configure_customize_github_copilot_vscode.html) | Separate ContosoInventory starter; VS Code-specific customization. |
| 16 | [Integrate Copilot SDK](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_16_develop_ai_enabled_apps_github_copilot_sdk.html) | Separate ContosoShop starter. First follow [SDK/CLI preparation](https://microsoftlearning.github.io/mslearn-github-copilot-dev/Instructions/Labs/LAB_AK_00_configure_github_copilot_sdk_lab.html). |

## Important boundaries

- General prerequisites include Git 2.48+, VS Code 1.116+, C# Dev Kit, and .NET SDK 9.0+ as specified by the exercises. Check each sample's target framework/runtime as well; installing a newer SDK alone does not ensure every older runtime is present.
- Exercises 13-14 additionally list SQL Server LocalDB, Python 3.11+, uv, and Specify CLI. The preparation page mentions SQLite too; do not assume that is a drop-in replacement for a particular starter. Follow the individual exercise's database requirements. LocalDB is Windows-specific.
- Exercise 16 requires an installed, authenticated GitHub Copilot CLI.
- Skillable learners should use the assigned platform instructions. This public catalog is a reference, not a guarantee of which labs their lab key includes.
