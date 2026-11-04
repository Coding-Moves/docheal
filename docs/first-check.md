# First check: a removed CLI option in Markdown

DocHeal's first local check will look for one possible kind of drift: a Python
command-line option is removed, but a guide still names it. This is the scope
for [issue #1](https://github.com/Coding-Moves/docheal/issues/1), not a working
checker yet.

## Input and behavior

The planned check takes two committed revisions in a local Git repository, one
explicit Python source file, and one explicit Markdown guide. The source file
must exist at both revisions; the guide is read at the newer revision. No
GitHub connection or AI service is needed. Issue #3 will settle the command
syntax and how invalid paths or revisions are reported.

In the source file, v1 will recognize literal long options passed directly to
`parser.add_argument()`, where `parser` is created by
`argparse.ArgumentParser()` in the same module. If an option exists at the older
revision but not the newer one, the check will look for that exact option in an
inline code span in the specified `.md` file. It will report a **possible**
drift finding with the old declaration and the current guide reference. It
will not guess the replacement option or edit the guide. Issue #2 will define
the finding's exact format.

For example, a small local repository could contain this `cli.py` at the base
revision:

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("--user-name")
```

At the newer revision, `cli.py` contains:

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("--display-name")
```

The `guide.md` file at both revisions still contains:

```markdown
Run the command with `--user-name`.
```

Given the two revisions and the paths `cli.py` and `guide.md`, DocHeal should
point to that guide reference as a possible stale instruction.

For a quiet case, make the same code change and update `guide.md` to contain:

```markdown
Run the command with `--display-name`.
```

There is no old option reference to report. It should also stay quiet if
`--user-name` remains declared as a compatibility option.

## Limits for this first version

- Only the specified files are checked. The guide must be Markdown, and the
  option reference must be inside an inline code span such as `--user-name`.
- Short options, computed option names, helper functions, and parser setup
  outside the stated pattern are outside scope. Renamed or deleted source
  files and uncommitted changes are outside scope too.
- A historical or migration guide may intentionally mention a removed option.
  A finding asks a maintainer to review it; it does not prove the guide wrong.
- Bad revisions, missing files, and Python that cannot be parsed must be
  reported as input errors, not as a clean result. Issue #3 will specify the
  exact error behavior.

The examples above can be made as two commits in a tiny local test repository.
The later implementation in issue #4 should test both outcomes without a
hosted service.
