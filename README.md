# learning-lerna
Playground for testing monorepo with conventional commits, lerna and github actions

## commitlint configuration
The configuration can be changed in the ./commitlint.config.js if required.

## tools
This monorepo uses lerna and github actions to automatically version two dummy packages by utilizing conventional commits. For this refer to the `version.yaml` workflow.

Furthermore it leverages the commitlint to check if the pushed commit into the main branch is written according to the conventional commits. The check happens in the `ci.yaml` file.

Only squashing PRs is allowed.

Husky is used to lint commit messages.

## possible next steps
An approach combining linting of the PR titles and squash-only merging with messages defaulting to pull request title. A workflow for it could go along something like this (not tested yet).
Alternatively, any string can be linted against commitlint rules programmatically (an example here: https://github.com/dreampulse/action-commitlint-pull-request-title/blob/main/README.md).
```
on:
  push:
  pull_request:
   types: [opened, synchronize]
jobs:
  commitlint:
    ...

      - name: Validate PR title with commitlint
        run: npx commitlint ${{ github.event.pull_request.title }} --verbose
```
