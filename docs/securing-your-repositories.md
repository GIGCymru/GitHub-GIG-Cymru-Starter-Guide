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
- Use the built-in `GITHUB_TOKEN` in workflows rather than PATs wherever possible.
- Use **fine-grained** PATs rather than classic PATs, and set an expiry on every token.
- Use two-factor authentication or passkeys on every account.

> **Further reading and information**
>
> [Security hardening for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)

## GitHub Advanced Security (GHAS)

GitHub Advanced Security is now offered as two products: **GitHub Secret Protection** and
**GitHub Code Security**. Together they provide these capabilities for NHS Wales repositories
(check with the GitHub GIG Cymru service team which are enabled for your organisation):

| **Feature** | **Product** | **What it does** |
| --- | --- | --- |
| **Secret scanning and push protection** | Secret Protection | Detects secrets (API keys, tokens, passwords) in code, and blocks pushes that contain them. |
| **Code scanning with CodeQL** | Code Security | Analyses code for vulnerabilities. Use *default setup* for the quickest start. |
| **Copilot Autofix** | Code Security | Suggests fixes for code scanning alerts (where Copilot is licensed). |
| **Dependency review** | Code Security | Flags vulnerable dependencies in a pull request before they are merged. |
| **Dependabot** | All repositories | Alerts on vulnerable dependencies and raises update pull requests. |

All repositories containing production code **SHOULD** have GHAS enabled. Contact the
GitHub GIG Cymru service team to enable GHAS for your organisation.

> **Practical tip**
>
> Enable *push protection* to block commits that contain known secret patterns before
> they ever reach the repository, and use CodeQL *default setup* to enable code scanning
> without writing a workflow.
>
> Alert on, and fix, high-severity findings first. Treat code scanning and secret scanning
> alerts as part of normal pull request review.

> **Further reading and information**
>
> [GitHub security features - GitHub Docs](https://docs.github.com/en/code-security/getting-started/github-security-features)
>
> [About push protection - GitHub Docs](https://docs.github.com/en/code-security/secret-scanning/introduction/about-push-protection)
>
> [About GitHub Advanced Security - GitHub Docs](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)
>
> [Securing your organization - GitHub Docs](https://docs.github.com/en/code-security/securing-your-organization)

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
- Enable *Dependabot version updates* for the `github-actions` ecosystem as well as your code dependencies, so pinned action versions are kept current.
- Use *grouped updates* to reduce the number of PRs raised.
- Review and merge Dependabot PRs promptly — treat security updates as high priority.

> **Further reading and information**
>
> [About Dependabot alerts - GitHub Docs](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)

## Branch protection and required status checks

Branch protection rules (or the newer **repository rulesets**, which are recommended) provide an important layer of defence against accidental or
malicious changes to critical branches. See [Branching and Source Control](branching-and-source-control.md)
for the recommended branch protection configuration.

Code scanning and dependency review checks **SHOULD** be added as required status checks (or
code scanning merge protection) on `main` and `release/*` branches.

## Data privacy

You **MUST** comply with NHS Wales data protection, privacy, and information security policies:

- Do **NOT** store Personal Identifiable Information (PII) or Special Category data in GitHub.
- Use anonymised or synthetic data in tests and code examples.
- Store sensitive configuration in a secrets manager (e.g. Azure Key Vault), not in the repository.

> **Further reading and information**
>
> [NHS Wales Information Governance](https://dhcw.nhs.wales/information-governance/)
