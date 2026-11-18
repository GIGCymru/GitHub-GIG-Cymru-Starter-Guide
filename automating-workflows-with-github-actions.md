# Automating Workflows with GitHub Actions

## What is GitHub Actions?

GitHub Actions is GitHub's built-in CI/CD platform. It allows you to automate workflows
directly in your repository — including building, testing, security scanning, and deploying
your code.

> **Further reading and information**
>
> [Understanding GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
>
> [AZ-400: Implement CI with Azure Pipelines and GitHub Actions - Microsoft Learn](https://learn.microsoft.com/en-gb/training/paths/az-400-implement-ci-azure-pipelines-github-actions/)

## Core concepts

| **Concept** | **Description** |
| --- | --- |
| **Workflow** | An automated process defined in a YAML file under `.github/workflows/`. |
| **Event** | The trigger that starts a workflow (e.g. `push`, `pull_request`, `schedule`, `workflow_dispatch`). |
| **Job** | A set of steps that run on the same runner. Jobs can run in parallel or sequentially. |
| **Step** | An individual task within a job — either a shell command or a reusable Action. |
| **Action** | A reusable unit of automation. Use actions from the GitHub Marketplace or write your own. |
| **Runner** | The machine that executes jobs. GitHub provides hosted runners; self-hosted runners can also be configured. |
| **Secret** | An encrypted variable stored at the repository or organisation level, used to pass sensitive values to workflows. |

## Core workflow characteristics

All GitHub Actions workflows **SHOULD** follow these practices:

- **Trigger on pull requests**: Run build and test workflows on every PR to validate changes before merge.
- **Trigger on push to main**: Run build and deployment workflows after merging to the main branch.
- **Pin action versions**: Pin third-party actions to a full-length commit SHA (add the version as a comment); this is the only way to use an action as an immutable release. Never use `@main` or `@latest`. Use Dependabot to keep pins up to date.
- **Use secrets for sensitive values**: Never hard-code credentials, tokens, or keys in workflow files.
- **Prefer OIDC over stored cloud credentials**: Use [OpenID Connect](https://docs.github.com/en/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect) to authenticate to Azure rather than long-lived secrets.
- **Set concurrency and timeouts**: Use `concurrency` to cancel superseded runs and `timeout-minutes` to stop runaway jobs.
- **Treat inputs as untrusted**: Never interpolate PR titles, branch names or other event data directly into `run:` scripts; pass them through environment variables.
- **Require manual approval for production deployments**: Use [Environments](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment) with required reviewers to gate production releases.

> **Practices to avoid**
>
> Do **NOT** use `@latest` when referencing actions. Pin to a full commit SHA (or at minimum a specific version tag such as `actions/checkout@v5`) to avoid unexpected breaking changes and supply chain attacks.
>
> Do **NOT** use `pull_request_target` or `workflow_run` with untrusted code checked out; this is a common route to leaked secrets.
>
> Do **NOT** store secrets in workflow YAML files or in the repository code. Always use GitHub Secrets or a secret manager.

## Recommended workflow structure

Store all workflow files in `.github/workflows/` using descriptive filenames:

| **Workflow file** | **Purpose** |
| --- | --- |
| `ci.yml` | Runs build and unit tests on every PR and push to main. |
| `security-scan.yml` | Runs CodeQL code scanning and dependency review (not needed if using code scanning default setup). |
| `deploy-staging.yml` | Deploys to the staging environment on merge to `develop`. |
| `deploy-production.yml` | Deploys to production on merge to `main`, with required approvals. |
| `release.yml` | Creates GitHub releases and tags on a version push. |

## Use reusable workflows

To avoid duplication across repositories, use *reusable workflows* to share common automation
patterns (e.g. a shared build pipeline, a shared security scan).

> **Further reading and information**
>
> [Reusing workflows - GitHub Docs](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

## Manage workflow permissions

Apply the *principle of least privilege* to workflow permissions:

- Set `permissions` explicitly in each workflow file.
- Use `contents: read` as the default.
- Only grant `write` permissions for the specific scopes that are required.

```yaml
permissions:
  contents: read
  pull-requests: write
```

Also set the organisation or repository default for `GITHUB_TOKEN` to **read-only**, and
restrict which actions may be used (for example, GitHub-authored and verified creators only).

## Example CI workflow

```yaml
name: ci
on:
  pull_request:
  push:
    branches: [main]

permissions:
  contents: read

concurrency:
  group: ci-${{ github.ref }}
  cancel-in-progress: true

jobs:
  build:
    runs-on: ubuntu-latest
    timeout-minutes: 15
    steps:
      - uses: actions/checkout@v5 # pin to a full commit SHA in real use
      - run: echo "build and test here"
```

> **Further reading and information**
>
> [Assigning permissions to jobs - GitHub Docs](https://docs.github.com/en/actions/using-jobs/assigning-permissions-to-jobs)

## GitHub Actions and Azure DevOps

GitHub Actions can trigger Azure DevOps Pipelines and vice versa. See
[Integrating with Azure DevOps](integrating-with-azure-devops.md) for guidance on connecting
the two platforms.
