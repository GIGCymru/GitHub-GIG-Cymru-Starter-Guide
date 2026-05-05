# GitHub Basics

## Core concepts and terminology

| **Concept** | **Description** |
| --- | --- |
| **Organisation** | A shared account for groups of people to collaborate across many repositories. Each NHS Wales organisation has its own GitHub org (e.g. `DHCW-Digital-Health-and-Care-Wales`). |
| **Repository** | A project container that holds files, version history, issues, and pull requests. Repositories can be public, internal, or private. |
| **Branch** | A parallel version of the repository used to develop features or fixes in isolation before merging back to the main branch. |
| **Commit** | A snapshot of changes to the repository at a specific point in time, identified by a unique SHA hash. |
| **Pull Request (PR)** | A request to merge changes from one branch into another. PRs enable code review, discussion, and automated checks before merging. |
| **Fork** | A personal copy of another user's repository. Forks allow you to freely experiment with changes without affecting the original project. |
| **Issue** | A way to track ideas, enhancements, tasks, and bugs. Issues can be linked to pull requests and project boards. |
| **GitHub Actions** | GitHub's built-in CI/CD platform for automating workflows such as build, test, and deploy pipelines. |
| **GitHub Packages** | A package registry for hosting and sharing packages (npm, NuGet, Maven, Docker, etc.) alongside your source code. |
| **GitHub Projects** | A planning and tracking tool for managing work across repositories using boards, tables, and roadmaps. |
| **Codespaces** | Cloud-hosted development environments that run directly in the browser or in VS Code, providing consistent, pre-configured setups. |
| **GitHub Copilot** | An AI-powered coding assistant that suggests code and helps with documentation (requires additional licensing). |

## Access levels and roles

GitHub GIG Cymru uses role-based access to manage what users can see and do.

| **Role** | **Description** |
| --- | --- |
| **Read** | View and clone repositories. Can open issues and comment on pull requests. |
| **Triage** | Everything in Read, plus manage issues and pull requests without write access. |
| **Write** | Everything in Triage, plus push commits and create branches. The standard role for contributors. |
| **Maintain** | Everything in Write, plus manage repository settings (excluding sensitive actions). |
| **Admin** | Full access to the repository, including sensitive and destructive actions. Reserved for repository owners. |
| **Organisation Owner** | Global administrator for the organisation. Manages billing, members, teams, and org-level settings. |

> **Practical tip**
>
> Always apply the *principle of least privilege*. Grant the minimum role needed for someone to do their job. Review access regularly and remove it promptly when no longer required.

## Key features used at NHS Wales

| **Feature** | **Primary use** |
| --- | --- |
| **Repositories** | Store and version all source code, infrastructure-as-code, and documentation. |
| **Pull Requests** | Review and approve code changes before they reach the main branch. |
| **GitHub Actions** | Automate build, test, security scanning, and deployment pipelines. |
| **GitHub Advanced Security (GHAS)** | Detect secrets, vulnerabilities, and code quality issues automatically. |
| **GitHub Projects** | Plan and track work items, epics, and milestones across repositories. |
| **Codespaces** | Provide consistent, cloud-based development environments (where licensed). |
| **GitHub Copilot** | Accelerate development with AI assistance (where licensed). |

## Visibility settings

Choose the appropriate visibility when creating a repository:

| **Visibility** | **Who can see it** | **When to use** |
| --- | --- | --- |
| **Private** | Only invited members and teams | Default for all NHS Wales project repositories. |
| **Internal** | All members of the GitHub Enterprise | Shared libraries and tools intended for cross-org use within NHS Wales. |
| **Public** | Anyone on the internet | Open source projects that have been approved for public release. |

> **Practices to avoid**
>
> Do **NOT** create public repositories without explicit approval. NHS Wales source code is
> private by default. Contact the GitHub GIG Cymru service team before making any repository public.
