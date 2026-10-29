# Contributing to DocHeal

Thanks for taking a look. DocHeal is still at the idea stage. There is no application to install or test yet, so the most useful early contributions are concrete examples of documentation drift and careful discussion of what the first check should cover.

## Start with an issue

Search the [open and closed issues](https://github.com/Coding-Moves/docheal/issues) before opening a new one. If you find an unclaimed issue you like, leave a comment before starting. For a new idea, explain the code change, the stale documentation it might leave behind, and what a useful warning would say. Small proposals are easier to evaluate than a broad promise to detect all outdated documentation.

For bugs, include the steps to reproduce, what you expected, and what happened. At present there is no runnable tool, so a bug report may be about the repository documentation or contributor workflow.

## Work locally

Fork the repository and make a branch for your change. You can clone your fork with Git, but there is no dependency installation, build, lint, or test command in this repository yet. Please do not add a toolchain just to make a documentation change.

Keep changes focused. Use plain English in docs, include a small example when it helps, and distinguish working behavior from plans. If you add code later, follow the conventions established by that part of the project and add a test for behavior that can regress. Avoid secrets, generated output, and unrelated cleanup.

## Open a pull request

Link the issue, explain what changed and why, and say how you checked it. For documentation-only changes, read the rendered Markdown and test any links you add. If a check cannot run because the tool or test suite does not exist yet, say that directly. Maintainers may ask for a smaller scope or a clearer example before merging.

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md).
