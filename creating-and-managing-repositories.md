# Creating and Managing Repositories

## Request a new repository

Before creating a new repository, check whether an existing repository already covers your
needs. Duplicate repositories create confusion and fragmentation.

To create a new repository, organisation members with the appropriate permissions can do so
directly. If you do not have permission, contact your Organisation Owner or GitHub GIG Cymru
service team.

When creating a repository, use these **RECOMMENDED** settings:

| **Property** | **Value** |
| --- | --- |
| **Owner** | Your NHS Wales GitHub organisation (not your personal account). |
| **Repository name** | Lowercase, hyphen-separated. See [naming conventions](#naming-conventions) below. |
| **Description** | A clear, searchable summary of the repository's purpose. |
| **Visibility** | `Private` by default. Use `Internal` for shared libraries. Never `Public` without approval. |
| **Initialise with README** | Yes — always initialise with a README. |
| **Add .gitignore** | Yes — choose the appropriate template for your language or framework. |
| **Choose a licence** | Select an appropriate open source licence if the repository is intended for public release. Leave blank for private repositories. |

> **Further reading and information**
>
> [Creating a new repository - GitHub Docs](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)

## Naming conventions

Name repositories in lowercase with hyphens. Use a consistent prefix to indicate the owning
team or product where helpful.

| **Component** | **Naming convention** | **Examples** |
| --- | --- | --- |
| **Repository** | Lowercase, hyphen-separated. `<product>-<purpose>` | `welsh-pas-api`, `ndr-data-pipeline`, `dhcw-shared-components` |
| **Release tag** | Semantic version `<Major>.<Minor>.<Patch>` | `1.0.0`, `2.3.1` |

> **Practical tip**
>
> Avoid abbreviations that are not well known. A clear, descriptive name is preferable to a short, cryptic one. Avoid spaces, underscores, and uppercase letters in repository names.

## Configure repository settings

After creating a repository, configure these settings:

### General settings

- **Default branch**: Ensure the default branch is named `main`.
- **Merge button**: Disable *Allow merge commits* unless required. Prefer *squash merging* for cleaner history.
- **Automatically delete head branches**: Enable this to keep the repository tidy after pull requests are merged.

### Branch protection

Protect your `main` (and `release/*`) branches to prevent accidental or unauthorised changes.
See [Branching and Source Control](branching-and-source-control.md) for full branch protection guidance.

### Repository topics

Add relevant [topics](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customising-your-repository/classifying-your-repository-with-topics) to your repository to improve discoverability across NHS Wales.

> **Examples of good practice**
>
> `nhs-wales`, `dhcw`, `python`, `dotnet`, `infrastructure-as-code`, `data-pipeline`

## README and documentation

Every repository **MUST** contain a `README.md` file at the root. The README **SHOULD**
include:

- A brief description of the repository's purpose.
- Prerequisites and setup instructions.
- How to build and run the project locally.
- How to contribute (or a link to `CONTRIBUTING.md`).
- Links to related documentation.

> **Further reading and information**
>
> [About READMEs - GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customising-your-repository/about-readmes)

## Archiving repositories

When a repository is no longer actively maintained, **SHOULD** archive it rather than delete
it. Archiving makes the repository read-only and clearly signals that it is no longer active,
while preserving the history for reference.

> **Further reading and information**
>
> [Archiving repositories - GitHub Docs](https://docs.github.com/en/repositories/archiving-a-github-repository/archiving-repositories)
