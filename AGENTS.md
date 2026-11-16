# Guidance for coding agents

This repository is the [Braveheart-Chess](https://github.com/Braveheart-Chess)
organisation's `.github` repository: `profile/README.md` is the page GitHub
shows on the organisation's profile. Read [README.md](README.md) for what the
project is and [CONTRIBUTING.md](CONTRIBUTING.md) for the full rules. The rules
below are the ones you MUST follow.

## Rules

- **Never push to `main`.** Every change goes through a pull request on a branch.
- **Commits are a single line**: `type(scope)?: subject`, at most 100 characters.
  Allowed types: `feat`, `fix`, `docs`, `chore`, `refactor`, `ci`, `build`, `perf`, `style`, `test`, `revert`.
  The only thing allowed after the header is a blank line and
  `Co-authored-by: Name <email>` trailers. No body text. Put details in the PR description.
- **Open PRs with a typed template** and fill in every section:

  ```sh
  gh pr create --template <feat|fix|docs|chore|refactor|ci>.md
  ```

  The PR title MUST be a valid Conventional Commit; squash merges use it as the commit message.
- **Merges are squash or rebase only.** Never create merge commits.
- **Run the repo's checks locally before opening the PR** (see below).
- **Files here can apply to every repository in the organisation.** GitHub
  uses a community health file in this repository (a PR template, issue
  templates, `CONTRIBUTING.md`, `SECURITY.md`, `CODE_OF_CONDUCT.md`) for any
  organisation repository that has none of its own. Add one only when it is
  meant for all of them, and say so in the PR.
- **The profile lists every public repository.** A new repository in the
  organisation gets a row in the table in `profile/README.md`.
- **The banner comes from braveheart-branding.** Paste its snippet verbatim;
  never copy the images here.
- **`CHANGELOG.md` is Release Please's.** Never edit it by hand.

## Before opening a PR

```sh
npm ci
npx commitlint --from origin/main --to HEAD --verbose
pre-commit run --all-files
```

## Things that need the owner

Repository settings and secrets, the release bot, and merging the Release
Please PR. List them in the PR instead of attempting them.
