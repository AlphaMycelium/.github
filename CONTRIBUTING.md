# Contribution Guidelines

**In addition to this document, please also view and follow the
[code of conduct](CODE_OF_CONDUCT.md).**

## Issues & Pull Requests

- If a template is provided for the type of issue you are opening, follow it.
  If not then use common sense and make sure to include all relevant information.
- Always format code snippets using code blocks. It makes it so much easier to
  read. (If you're referencing some code from within the repository, you can
  also highlight the lines on GitHub and select "copy permalink" to embed it
  in an issue or comment).
- Search for similar issues (both open and closed) before opening a new one.
- Sometimes I find it useful to do [rubber duck debugging][rubber-duck]
  in comments. Feel free to do the same.
- Use :thumbsup: and :thumbsdown: reactions to vote on features and pull
  requests you like or dislike.
- Use [closing keywords][closing-words] in pull requests when you have fixed
  an issue.
- Use draft PRs if something is still a work-in-progress.

[rubber-duck]: https://en.wikipedia.org/wiki/Rubber_duck_debugging

## Commits

A lot of my repositories use tools such as [Python Semantic Release][psr]
to automatically publish new versions. This requires commit messages to follow
[the Angular commit style][angular] in order to be recognized. For simplicity
this style is used whether automatic releases are enabled or not.

The most important parts are to include the type of change at the beginning of
the subject line, and list any breaking changes in the description.

```
type(scope): change

Description...

BREAKING CHANGE: Words...

More description...

Fixes #42
```

The scope and brackets are optional, and does not currently matter for semantic
release. As such there is no real need to include it.

The available change types are:

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

You should also make sure to mention any fixed issues at the end of the commit
using [closing keywords][closing-words]. This allows GitHub to automatically
close issues when pull requests are merged.

Some example commits:

```
fix: fix bug X
```

```
feat: add feature Z

BREAKING CHANGE: removed feature Y
```

```
ci(github): update GitHub Actions workflow

Insert useful description here
```

[psr]: https://github.com/relekang/python-semantic-release
[angular]: https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-guidelines
[closing-words]: https://help.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword


# Collaboration Guidelines

*If you are not added as a collaborator on any of my repositories then you
may stop reading now.*

## Merging Pull Requests

I prefer the use of squashing to merge PRs. Here's why:

- Merge commits can't follow the commit style guide above.
- Rebasing makes the committer different to the author, which I don't like.
- Unlike rebasing, squashing allows you to edit the commit message before
  merge. This can be used to fix up the commit style (see below).

When you merge, be sure to go through the following steps:

1. Read the diff. All of it. **Always.**
2. If the changes are to anything other than docs, test them when possible.
   (If automated tests exist for the repo, I will have added them to GitHub
   Actions.)
3. Submit a review. You can also use the comment box for approvals to say thanks
   for the PR.
   - Some repos have branch protection set up to require a minimum number of
     reviews before merging. If this requirement hasn't been reached yet, you
     can stop after this step.
   - [Code owners][code-owners] may be used to require a review from a specific
     person (usually me) on the most important files.
4. Ensure that the PR looks ready to merge.
   - Any task lists in the description are complete.
   - Tests passing.
   - No comments saying "still a work in progress" or similar.
5. Squash and merge. Edit the commit message:
   1. Ensure the change type in the subject is correct.
   2. Ensure all  breaking changes are described and are in paragraphs starting
      with `BREAKING CHANGE:`.
   3. Delete any useless information from the description (GitHub combines the
      commit messages when squashing, unimportant ones like style changes can
      be removed).
   4. Check for typos.
6. The head branch should be automatically deleted if it is not on a fork.
   If it isn't, do it manually, and mention @AlphaMycelium to fix the settings.

[code-owners]: https://help.github.com/en/github/creating-cloning-and-archiving-repositories/about-code-owners
