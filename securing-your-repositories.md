# Securing Your Repositories

Security is a shared responsibility. You **MUST** follow these essential practices to ensure
robust security for all NHS Wales GitHub repositories.

## Essential security practices

- Review repository and team access **at least quarterly** and apply the *principle of least privilege*.
- Remove access **as soon as** a user no longer requires it.
- Enable **GitHub Advanced Security (GHAS)** on all repositories containing production code or sensitive logic.
- Never store secrets, credentials, or patient-identifiable data in any repository.
- Rotate Personal Access Tokens (PATs) every **90 days** and use fine-grained tokens with minimum required scopes.
- Prefer **GitHub Apps** or **OIDC-based authentication** over PATs for service integrations.

> **Further reading and information**
>
> [Security hardening for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)

## GitHub Advanced Security (GHAS)

GitHub Advanced Security provides three key capabilities for NHS Wales repositories:

| **Feature** | **What it does** |
| --- | --- |
| **Code scanning** | Automatically analyses code for vulnerabilities using CodeQL and other tools. |
| **Secret scanning** | Detects accidentally committed secrets (API keys, tokens, passwords) and alerts you. |
| **Dependency review** | Flags vulnerable dependencies before they are merged via a pull request. |

All repositories containing production code **SHOULD** have GHAS enabled. Contact the
GitHub GIG Cymru service team to enable GHAS for your organisation.

> **Practical tip**
>
> Enable GHAS *push protection* to block commits that contain known secret patterns before
> they ever reach the repository.

> **Further reading and information**
>
> [About GitHub Advanced Security - GitHub Docs](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)
>
> [Enabling GitHub Advanced Security for your organisation - GitHub Docs](https://docs.github.com/en/organisations/keeping-your-organisation-secure/managing-security-settings-for-your-organisation/enabling-github-advanced-security-for-your-organisation)

## Secret scanning

Secret scanning is **RECOMMENDED** on all repositories. When a secret is detected:

1. **Immediately revoke** the exposed credential at the source (e.g. regenerate the API key or token).
2. Remove the secret from the repository history using [git-filter-repo](https://github.com/newren/git-filter-repo) or contact the GitHub GIG Cymru team for assistance.
3. Report the incident via your organisation's information security incident process.

> **Practices to avoid**
>
> Do **NOT** commit the following to any repository, including private ones:
>
> - Passwords or passphrases
> - API keys or access tokens
> - Connection strings containing credentials
> - Private keys or certificates
> - Patient or staff personal data

## Dependabot and dependency updates

Enable **Dependabot** to automatically detect and alert on vulnerable dependencies, and
optionally to raise pull requests for version updates.

- Enable *Dependabot alerts* on all repositories.
- Enable *Dependabot security updates* for automatic PR creation on vulnerable dependencies.
- Review and merge Dependabot PRs promptly — treat security updates as high priority.

> **Further reading and information**
>
> [About Dependabot alerts - GitHub Docs](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)

## Branch protection and required status checks

Branch protection rules provide an important layer of defence against accidental or
malicious changes to critical branches. See [Branching and Source Control](branching-and-source-control.md)
for the recommended branch protection configuration.

All GHAS checks (code scanning, secret scanning, dependency review) **SHOULD** be added as
required status checks on `main` and `release/*` branches.

## Data privacy

You **MUST** comply with NHS Wales data protection, privacy, and information security policies:

- Do **NOT** store Personal Identifiable Information (PII) or Special Category data in GitHub.
- Use anonymised or synthetic data in tests and code examples.
- Store sensitive configuration in a secrets manager (e.g. Azure Key Vault), not in the repository.

> **Further reading and information**
>
> [NHS Wales Information Governance](https://dhcw.nhs.wales/information-governance/)
