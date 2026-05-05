# Integrating with Azure DevOps

Many NHS Wales teams use both GitHub and Azure DevOps. This section describes how the two
platforms can be integrated to support end-to-end software delivery workflows.

## When to use GitHub vs Azure DevOps

| **Capability** | **Preferred platform** |
| --- | --- |
| **Source code hosting** | GitHub |
| **Pull requests and code review** | GitHub |
| **CI/CD pipelines** | GitHub Actions (for GitHub-hosted code) or Azure Pipelines (for cross-platform or Azure-centric deployments) |
| **Work item tracking (backlogs, sprints)** | Azure Boards |
| **Package management** | GitHub Packages or Azure Artifacts |
| **Test management** | Azure Test Plans |
| **Wikis and documentation** | GitHub Wikis or the [DHCW Software Engineering Handbook](https://gigcymru.github.io/dhcw-software-engineering-handbook/) |

> **Practical tip**
>
> Teams that primarily use GitHub for source control can still use Azure Boards for sprint
> planning and work item tracking by connecting GitHub to Azure DevOps. This allows you to
> link GitHub commits and pull requests to Azure Boards work items.

## Connect GitHub to Azure Boards

Linking GitHub to Azure Boards enables traceability between code changes and work items.

To connect a GitHub repository to an Azure DevOps project:

1. In your Azure DevOps project, go to **Project Settings** > **GitHub connections**.
2. Click **New connection** and authenticate with your GitHub account.
3. Select the GitHub organisation and repositories to connect.
4. Once connected, you can reference Azure Boards work items in GitHub commits and PRs using the `AB#<work-item-id>` syntax.

> **Examples of good practice**
>
> Commit message: `Add patient search endpoint AB#450447`
>
> PR description: `Implements the patient lookup API. Closes AB#450447.`

> **Further reading and information**
>
> [Connect Azure Boards to GitHub - Azure DevOps | Microsoft Learn](https://learn.microsoft.com/en-gb/azure/devops/boards/github/connect-to-github?view=azure-devops)

## Trigger Azure Pipelines from GitHub

Azure Pipelines can be triggered by changes in a GitHub repository. This is useful when your
deployment infrastructure is managed in Azure DevOps but your source code is in GitHub.

To connect a GitHub repository to Azure Pipelines:

1. In your Azure DevOps project, create a new Pipeline.
2. Select **GitHub** as the source.
3. Authenticate and select your repository.
4. Azure Pipelines will create a `azure-pipelines.yml` file in your repository.

> **Further reading and information**
>
> [Build GitHub repositories - Azure Pipelines | Microsoft Learn](https://learn.microsoft.com/en-gb/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml)

## Use GitHub Actions to call Azure DevOps APIs

GitHub Actions can also interact with Azure DevOps through the REST API or available
marketplace actions. Common scenarios include:

- Triggering an Azure Pipeline run from a GitHub Actions workflow.
- Updating Azure Boards work items from a GitHub Actions step.
- Publishing test results to Azure Test Plans from a GitHub Actions workflow.

> **Further reading and information**
>
> [Azure DevOps REST API reference | Microsoft Learn](https://learn.microsoft.com/en-gb/rest/api/azure/devops/)
>
> [GitHub Actions marketplace - Azure DevOps actions](https://github.com/marketplace?query=azure+devops)

## GitHub Advanced Security and Azure DevOps

GitHub Advanced Security (GHAS) results can be surfaced in Azure DevOps using the
*Microsoft Security DevOps* extension, providing a unified security view across both platforms.

> **Further reading and information**
>
> [Connect GitHub to Defender for DevOps - Azure Pipelines | Microsoft Learn](https://learn.microsoft.com/en-gb/azure/defender-for-cloud/quickstart-onboard-github)

## Recommended integration pattern

For NHS Wales teams using both platforms, the following pattern is **RECOMMENDED**:

1. **Source code** lives in GitHub (version control, PRs, code review, GHAS).
2. **Work items** are tracked in Azure Boards (linked to GitHub PRs and commits via `AB#`).
3. **CI pipelines** run in GitHub Actions (build, test, GHAS scanning on every PR).
4. **CD pipelines** deploy via Azure Pipelines (using GitHub as the source) for Azure-hosted services.
5. **Packages** are published to GitHub Packages or Azure Artifacts depending on the consumer audience.
