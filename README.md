# DocHeal

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
