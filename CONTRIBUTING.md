# Contribution Guide

Thank you for your contribution! Please refer to the README files in each repository for detailed contribution guidelines.

The following are some general tips.

> Forked from [Anthony's](https://github.com/antfu/contribute).

## 👨‍💻 Repository Setup

We use [`pnpm`](https://pnpm.io/) for most of the projects.

To set the repository up:

| Step                                                                                                     | Command           |
| -------------------------------------------------------------------------------------------------------- | ----------------- |
| 1. Install [Node.js](https://nodejs.org/), using the [latest LTS](https://nodejs.org/en/about/releases/) | -                 |
| 2. [Enable Corepack](#corepack)                                                                          | `corepack enable` |
| 4. Install dependencies under the project root                                                           | `pnpm i`          |

## 🙌 Sending Pull Request

### Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/) for commit messages, which allows the changelog to be auto-generated based on the commits. Please read the guide through if you aren't familiar with it already.

Only `fix:` and `feat:` will be presented in the changelog.

Note that `fix:` and `feat:` are for **actual code changes** (that might affect logic).
For typo or document changes, use `docs:` or `chore:` instead:

- ~~`fix: typo`~~ -> `docs: fix typo`

### Pull Request

If you don't know how to send a Pull Request, we recommend reading [the guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

When sending a pull request, make sure your PR's title also follows the [Commit Convention](#commit-convention).

If your PR fixes or resolves an existing issue, please add the following line in your PR description (replace `123` with a real issue number):

```markdown
fix #123
```

This will let GitHub know the issues are linked, and automatically close them once the PR gets merged. Learn more at [the guide](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword).

It's ok to have multiple commits in a single PR, you don't need to rebase or force push for your changes as we will use `Squash and Merge` to squash the commits into one commit when merging.

## 📖 References

### Corepack

#### TL;DR

To enable it, run

```bash
corepack enable
```

You only need to do it once after Node.js is installed.

#### What's Corepack

[Corepack](https://nodejs.org/api/corepack.html) makes sure you are using the correct version for package manager when you run corresponding commands. Projects might have `packageManager` field in their `package.json`.

Under projects with configuration as shown on the right, corepack will install `v7.1.5` of `pnpm` (if you don't have it already) and use it to run your commands. This makes sure everyone working on this project have the same behavior for the dependencies and the lockfile.

```jsonc
// package.json
{
  "packageManager": "pnpm@7.1.5"
}
```

### ESLint

We use [ESLint](https://eslint.org/) and [Prettier](https://prettier.io/) for linting and formatting.
