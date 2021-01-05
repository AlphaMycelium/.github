# Contribution Guidelines

**In addition to this document, please read the
[code of conduct](CODE_OF_CONDUCT.md).**

## Issues

- Use the :thumbsup: reaction on feature requests you like or bugs you are
  also experiencing.
- Search for similar issues before opening a new one.
- When including code in issues, surround it with a markdown code block.

## Pull Requests

- Use [closing keywords][closing-words] when you have fixed an issue.
- Mark your pull request as draft if it is a work-in-progress.
- Feel free to add reviews even if you don't have push access.

## Code

- Keep your code easily readable and understandable.
- Add relevant comments to explain why things are done.
  - Avoid unnecessary comments such as "Set x to 42".
- Split code into multiple functions or files to reduce complexity.
- Automatic beautification will be used if I want to enforce a specific style.

## Commits

I sometimes use tools such as [Python Semantic Release][psr] to automatically
publish new versions. This requires commit messages to follow a specific
format, the [Angular commit style][angular-style].

```
type: add a cool new feature

This paragraph should describe why this change was made, if it is not obvious
from the subject line. It is NOT necessary to describe how it was implemented
as that can be seen from the diff.

BREAKING CHANGE: Feature X has been removed, use feature Y instead.

Closes #42, fixes #23
```

The available types are:

- **feat**: A new feature, or improvement of an existing one
- **fix**: Fixing a bug
- **perf**: Improving performance
- **docs**: Changes to documentation only (if you modify docs alongside
  something else, use the correct type for the other change)
- **refactor**: A code change which neither fixes a bug nor adds a feature
- **style**: Changes to the formatting of code which do not affect its meaning
- **test**: Adding or changing tests
- **ci**: Changes to CI configurations etc.
- **build**: Changes to dependencies or build systems
- **chore**: Other non-code-related changes

You should use [closing keywords][closing-words] to mention any fixed issues.
This will automatically close the issue once the fix is merged.

[psr]: https://github.com/relekang/python-semantic-release
[angular-style]: https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-guidelines
[closing-words]: https://help.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword
