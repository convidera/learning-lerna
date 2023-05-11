# learning-lerna
Playground for testing monorepo with conventional commits, lerna and github actions

## commitlint configuration
The configuration can be changed in the ./commitlint.config.js if required.

## tools
This monorepo uses lerna and github actions to automatically version two dummy packages by utilizing conventional commits. For this refer to the `version.yaml` workflow.

Furthermore it leverages the commitlint to check if the pushed commit into the main branch is written according to the conventional commits. The check happens in the `ci.yaml` file.

Only squashing PRs is allowed.

Husky is used to lint commit messages.
