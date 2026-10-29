# DocHeal

Git app to make your docs update as code.

## Glossary

- **Documentation drift:** When documentation no longer matches the actual code or current project behavior.
- **Finding:** A reported issue that may indicate a problem in the documentation.
- **Source reference:** A pointer to the code or other source material used to check whether documentation is accurate.
- **Documentation reference:** A pointer to the part of the documentation being discussed or checked.
- **False positive:** A reported finding that is not actually a problem.

### Example

Suppose a README says a function accepts two arguments, but the source code shows it accepts three. This mismatch is documentation drift. A finding could point to the README text, while the source reference points to the function's code and the documentation reference points to the relevant README section. If the reported mismatch turns out to be intentional or incorrect, it may be a false positive.

*These terms describe the planned workflow; this example does not imply that an automated checker is already running.*
**Keep documentation healthy as code changes.**

DocHeal is an early [Coding Moves Lab](https://codingmoves.netlify.app/lab/) project. The idea is simple: when code changes, help maintainers find the docs that may need another look.

Imagine an API field changes from `user_name` to `display_name`, but a guide still tells readers to use `user_name`. That guide has drifted from the code. DocHeal should point to the change and the guide so a person can decide what to fix. It should not silently rewrite the page or pretend it can prove every document correct.

## Where it stands

This is an **idea-stage repository**. There is no checker, CLI, package, or test suite yet. The repository contains the project direction, an MIT license, and contributor guidance. The [starter issues](https://github.com/Coding-Moves/docheal/issues) lay out the first pieces of work. Nothing here is a released DocHeal tool.

## The first version we want to build

The first version should run locally and do one narrow job well:

1. Read a set of code changes.
2. Find documentation that may be affected.
3. Apply a small, deterministic check.
4. Report possible drift with references to the code and documentation.

We still need to choose the first check, supported inputs, and report format. Those decisions come before a package or installation guide. A local checker should work without an AI key or a hosted service.

If that proves useful, we can consider more checks, repository configuration, and a GitHub pull request integration. AI-assisted analysis might help with harder cases later, but it would be optional. Findings should always give maintainers enough evidence to review them, and any GitHub integration should use only the permissions it needs.

## Getting started

There is nothing to install or run today. Read this README and [CONTRIBUTING.md](CONTRIBUTING.md), then look at the [starter issues](https://github.com/Coding-Moves/docheal/issues). The [good first issues](https://github.com/Coding-Moves/docheal/labels/good%20first%20issue) are small documentation tasks that do not need an unfinished checker.

If you have seen documentation drift in a real project, [open an issue](https://github.com/Coding-Moves/docheal/issues) and describe the code change, the stale documentation, and what a useful warning would say. Please remove private details. For a problem with this repository or its docs, choose the bug report form.

Small, self-contained examples are especially helpful. The [examples guide](examples/README.md) explains the format. Before a large pull request, discuss the behavior in an issue so we agree on the scope. Please read our [Code of Conduct](CODE_OF_CONDUCT.md) as well.

## Roadmap

- [ ] Agree on the first supported drift case and input format.
- [ ] Gather positive examples and cases that should stay quiet.
- [ ] Define a clear finding and report format.
- [ ] Build and test the first local check.
- [ ] Document real commands, configuration, and limits once they exist.
- [ ] Explore pull request checks after the local workflow is useful.

DocHeal will stay in [Coding Moves Lab](https://codingmoves.netlify.app/lab/) while we test the idea. After a first working release, we plan to move its website listing to [Coding Moves Open Source](https://codingmoves.netlify.app/open-source/).

## License

DocHeal is licensed under the [MIT License](LICENSE).
