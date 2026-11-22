# Guidance for coding agents

This repository is the [Braveheart-Chess](https://github.com/Braveheart-Chess)
organisation's `.github` repository: `profile/README.md` is the page GitHub
shows on the organisation's profile. Read [README.md](README.md) for what the
project is and [CONTRIBUTING.md](CONTRIBUTING.md) for the full rules. The rules
below are the ones you MUST follow.

## Rules

- **Never push to `main`.** Every change goes through a pull request on a branch.
- **Commits are a single line**: `type(scope): subject`, at most 100 characters, with a lowercase imperative subject and no trailing period. Types: `feat`, `fix`, `perf`, `revert`, `docs`, `refactor`, `test`, `build`, `ci`, `style`, `chore`; never invent another. Scope: exactly one of `SCOPES` in `commitlint.config.mjs` (the Scopes table in CONTRIBUTING.md); never invent one, and if none fits, ask. The only thing allowed after the header is a blank line and `Co-authored-by: Name <email>` trailers. No body text. Put details in the PR description.
- **PR titles are valid commit headers**, scope included; squash merges use the title as the commit message.
- **PR bodies use the template's sections, in order, every one filled in**; write "n/a" rather than deleting one:

  ```sh
  gh pr create --title "type(scope): subject" --body-file <file>
  ```
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
npm run test:commitlint   # the commit rules, the scopes table and the fixtures
npx commitlint --from origin/main --to HEAD --verbose
pre-commit run --all-files
```

## Things that need the owner

Repository settings and secrets, the release bot, and merging the Release
Please PR. List them in the PR instead of attempting them.
