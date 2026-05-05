# Essential Good Practice Checklist

Use this checklist to verify that your repository and workflows meet the minimum standards
expected for NHS Wales GitHub projects.

## Repository setup

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 1 | Your repository is owned by the correct NHS Wales GitHub organisation (not a personal account). | ☐ | [Creating and Managing Repositories](creating-and-managing-repositories.md) |
| 2 | Your repository name follows the lowercase hyphen-separated naming convention. | ☐ | [Naming conventions](creating-and-managing-repositories.md#naming-conventions) |
| 3 | Your repository has a clear description and relevant topics. | ☐ | [Configure repository settings](creating-and-managing-repositories.md#configure-repository-settings) |
| 4 | Repository visibility is `Private` or `Internal` (not `Public` unless approved). | ☐ | [Visibility settings](github-basics.md#visibility-settings) |
| 5 | Your repository contains a `README.md` with setup and contribution instructions. | ☐ | [README and documentation](creating-and-managing-repositories.md#readme-and-documentation) |
| 6 | A `.gitignore` file appropriate to your technology stack is present. | ☐ | [Creating and Managing Repositories](creating-and-managing-repositories.md) |

## Access and permissions

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 7 | Access follows the principle of least privilege. | ☐ | [Managing Users, Teams and Permissions](managing-users-teams-and-permissions.md) |
| 8 | Two-factor authentication (2FA) is enabled for all users. | ☐ | [Getting Started](getting-started.md) |
| 9 | Admin access is restricted to repository owners only. | ☐ | [Recommended team permission levels](managing-users-teams-and-permissions.md#recommended-team-permission-levels-for-repositories) |
| 10 | Access is reviewed at least quarterly and removed promptly when no longer required. | ☐ | [Review and audit access](managing-users-teams-and-permissions.md#review-and-audit-access) |

## Branching and source control

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 11 | Branch protection rules are configured on `main` and `release/*` branches. | ☐ | [Configure branch protection rules](branching-and-source-control.md#configure-branch-protection-rules) |
| 12 | All changes to `main` and release branches go through a pull request. | ☐ | [Pull Requests and Code Review](pull-requests-and-code-review.md) |
| 13 | Pull requests require at least one approving review before merging. | ☐ | [Configure branch protection for pull requests](pull-requests-and-code-review.md#configure-branch-protection-for-pull-requests) |
| 14 | Feature branches are linked to issues and deleted after merging. | ☐ | [Naming conventions](branching-and-source-control.md#naming-conventions) |
| 15 | Releases are tagged using Semantic Versioning (SemVer 2.0.0). | ☐ | [Branching and Source Control](branching-and-source-control.md) |

## Automation and CI/CD

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 16 | A CI workflow runs build and tests on every pull request. | ☐ | [Automating Workflows with GitHub Actions](automating-workflows-with-github-actions.md) |
| 17 | Action versions are pinned to a specific version tag or commit SHA. | ☐ | [Core workflow characteristics](automating-workflows-with-github-actions.md#core-workflow-characteristics) |
| 18 | Workflow permissions follow the principle of least privilege. | ☐ | [Manage workflow permissions](automating-workflows-with-github-actions.md#manage-workflow-permissions) |
| 19 | Production deployments require manual approval via a GitHub Environment. | ☐ | [Core workflow characteristics](automating-workflows-with-github-actions.md#core-workflow-characteristics) |

## Security

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 20 | GitHub Advanced Security (GHAS) is enabled (code scanning, secret scanning, dependency review). | ☐ | [Securing Your Repositories](securing-your-repositories.md) |
| 21 | Dependabot alerts and security updates are enabled. | ☐ | [Dependabot and dependency updates](securing-your-repositories.md#dependabot-and-dependency-updates) |
| 22 | No secrets, credentials, or PII are committed to the repository. | ☐ | [Data privacy](securing-your-repositories.md#data-privacy) |
| 23 | Personal Access Tokens (PATs), if used, expire within 90 days and use minimum required scopes. | ☐ | [Essential security practices](securing-your-repositories.md#essential-security-practices) |

## Azure DevOps integration (if applicable)

| **No.** | **Checklist item** | **Done** | **Guide** |
| --- | --- | --- | --- |
| 24 | GitHub is connected to Azure Boards and commits/PRs reference work items using `AB#<id>`. | ☐ | [Connect GitHub to Azure Boards](integrating-with-azure-devops.md#connect-github-to-azure-boards) |
| 25 | The integration pattern (GitHub for source, Azure DevOps for work items/deployment) is documented in the README. | ☐ | [Recommended integration pattern](integrating-with-azure-devops.md#recommended-integration-pattern) |
