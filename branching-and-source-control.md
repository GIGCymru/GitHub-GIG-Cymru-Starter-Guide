# Branching and Source Control

Following the practices in this section aligns with the
[Using Source Control](https://gigcymru.github.io/dhcw-software-engineering-handbook/using-source-control/introduction/)
standard, improving traceability and code quality across NHS Wales projects.

## Choose a branching strategy

You have freedom to choose your branching strategy, but you **SHOULD** follow these key
practices to maintain simplicity and consistency:

- **Use feature branches**: Develop new features and fix bugs in dedicated branches.
- **Merge through pull requests (PRs)**: Integrate changes into the main branch using PRs only.
- **Keep the main branch clean**: Ensure `main` is always stable and deployable.
- **Tag releases**: Tag every release commit to ensure traceability and version identification.

## Naming conventions

Use lowercase names with hyphens for all branches and tags.

| **Branch type** | **Naming convention** | **Examples** |
| --- | --- | --- |
| **Main** | `main` | `main` |
| **Develop** | `develop` | `develop` |
| **Feature** | `feature/<issue-number>-<short-description>` | `feature/123-add-patient-search` |
| **Release** | `release/<version>` | `release/2.0.0` |
| **Bug fix** | `bugfix/<issue-number>-<short-description>` | `bugfix/456-fix-null-reference` |
| **Hot fix** | `hotfix/<issue-number>-<short-description>` | `hotfix/789-critical-auth-patch` |
| **Release tag** | `<Major>.<Minor>.<Patch>` | `2.0.0`, `1.3.1` |

> **Practical tip**
>
> Always link branches to a corresponding GitHub Issue or work item. This creates
> traceability between code changes and planned work.
>
> Delete feature branches after merging to keep the repository tidy.

## Configure branch protection rules

Protect your `main` and `release/*` branches with branch protection rules. These rules
**SHOULD** be configured as follows:

- **Require pull request reviews before merging**: Ensure at least one approved review before merging.
- **Require status checks to pass**: Block merges when CI checks fail (e.g. build, tests, GHAS).
- **Require branches to be up to date before merging**: Prevent stale branches from being merged.
- **Restrict who can push to matching branches**: Limit direct pushes to branch administrators only.
- **Require signed commits**: Where possible, enforce GPG-signed commits for auditability.

> **Further reading and information**
>
> [About protected branches - GitHub Docs](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)

## Write good commit messages

Good commit messages help your team understand *why* a change was made, not just *what* changed.

A well-formed commit message **SHOULD**:

- Use the imperative mood in the subject line (e.g. `Add patient search endpoint` not `Added...`).
- Be concise but descriptive (aim for 50–72 characters in the subject line).
- Reference the related issue number (e.g. `Fixes #123`).
- Separate the subject from an optional body with a blank line.

> **Examples of good practice**
>
> `Add patient satisfaction analysis (#450)`
>
> `Fix null reference in data import pipeline (#627)`
>
> `Update README with setup instructions`

> **Practices to avoid**
>
> `fix`
>
> `wip`
>
> `asdfgh`

## Working with large files

Git is optimised for text files. For large binary files (e.g. images, data exports, compiled
binaries), follow these guidelines:

- Files over **100 MB** **MUST NOT** be committed directly to a repository.
- Use **Git LFS (Large File Storage)** for large assets that must be versioned.
- Use cloud storage links or NHS Wales approved file stores for data files.

> **Practices to avoid**
>
> Do **NOT** commit patient data, production database exports, or sensitive datasets to
> any GitHub repository — including private ones. Use dummy or anonymised data only.

> **Further reading and information**
>
> [About Git Large File Storage - GitHub Docs](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage)
