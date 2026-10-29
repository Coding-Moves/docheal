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
