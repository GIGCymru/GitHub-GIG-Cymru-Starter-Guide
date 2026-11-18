# Pull Requests and Code Review

## Why use pull requests?

Pull requests (PRs) are the primary mechanism for contributing code changes to a shared
repository. They provide:

- **Peer review**: Colleagues can review, comment on, and approve changes before they are merged.
- **Automated checks**: CI pipelines and security scans run automatically on every PR.
- **Traceability**: PRs link code changes to issues, providing an audit trail.
- **Discussion**: Inline comments and review threads enable structured conversation about the code.

All changes to `main` and `release/*` branches **MUST** go through a pull request.

## Create a pull request

1. Push your feature branch to GitHub.
2. Navigate to the repository on GitHub.com.
3. Click **Compare & pull request** (this appears automatically after a push) or go to the **Pull requests** tab and click **New pull request**.
4. Select the correct base branch (usually `main` or `develop`).
5. Fill in the PR description (see [below](#write-a-good-pr-description)).
6. Assign reviewers and link relevant issues.
7. Click **Create pull request**.

## Write a good PR description

A good PR description helps reviewers understand the context and purpose of the change
without having to read every line of code.

A PR description **SHOULD** include:

- A brief summary of *what* changed and *why*.
- Links to related issues (use `Closes #<issue-number>` to auto-close the issue on merge).
- Any relevant testing steps or screenshots.
- Notes on deployment considerations or configuration changes.

> **Examples of good practice**
>
> **Summary**: Adds a new search endpoint for patient records.
>
> **Motivation**: Required to support the new patient portal search feature (#123).
>
> **Testing**: Covered by unit tests in `PatientSearchTests.cs`. Tested manually against dev environment.
>
> **Closes** #123

## Review pull requests

When reviewing a pull request, you **SHOULD**:

- Review the code for correctness, security, and maintainability.
- Check that tests cover the new or changed behaviour.
- Leave constructive, specific feedback using inline comments.
- Approve the PR only when you are confident it meets the team's Definition of Done.

> **Practical tip**
>
> Use the *Request changes* option when blocking issues are found. Use *Comment* for
> non-blocking suggestions. Use *Approve* only when the PR is ready to merge.

> **Further reading and information**
>
> [About pull request reviews - GitHub Docs](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)

## Configure branch protection for pull requests

Branch protection rules **SHOULD** be configured to enforce PR-based workflows on protected
branches. Recommended settings:

- **Require a minimum number of reviewers**: At least one approval **SHOULD** be required before merging.
- **Dismiss stale pull request approvals**: Re-require review when new commits are pushed.
- **Require review from Code Owners**: Where a `CODEOWNERS` file is defined, require approval from the relevant code owners.
- **Require status checks**: All CI checks and security scans **MUST** pass before merging.
- **Require conversation resolution**: All review comments **MUST** be resolved before merging.

> **Further reading and information**
>
> [About code owners - GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customising-your-repository/about-code-owners)

## Merge strategies

Choose the merge strategy that best fits your team's workflow:

| **Strategy** | **When to use** |
| --- | --- |
| **Squash and merge** | **RECOMMENDED** for most feature branches. Produces a clean, linear history with one commit per PR. |
| **Merge commit** | Use when you want to preserve the full branch history. |
| **Rebase and merge** | Use when you want a linear history without a merge commit and individual commits are meaningful. |

> **Practices to avoid**
>
> Do **NOT** merge PRs without at least one peer review.
>
> Do **NOT** bypass branch protection rules — even for urgent fixes. Use a hotfix branch and follow the standard PR process.
