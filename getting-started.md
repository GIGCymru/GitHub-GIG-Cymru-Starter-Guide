# Getting Started

## Request access

All NHS Wales staff access GitHub GIG Cymru through their organisation's GitHub Enterprise
account. Access is managed through NHS Wales Active Directory via Single Sign-On (SSO).

To get access:

1. Contact your local IT service desk and request access to **GitHub GIG Cymru**.
2. Specify which GitHub organisation you need access to (e.g. `DHCW-Digital-Health-and-Care-Wales`).
3. Once provisioned, sign in at [https://github.com](https://github.com) using your NHS Wales credentials.
4. Accept the organisation invitation in GitHub to complete onboarding.

> **Further reading and information**
>
> [List of GIG Cymru organisations on GitHub](https://github.com/GIGCymru)

## Request additional features

Some features require additional licensing or approval:

| **Feature** | **How to request** |
| --- | --- |
| **GitHub Codespaces** | Contact your local budget holder, then raise a request with the GitHub GIG Cymru service team. |
| **GitHub Copilot** | Contact your local budget holder, then raise a request with the GitHub GIG Cymru service team. |
| **GitHub Advanced Security (GHAS)** | Contact the GitHub GIG Cymru service team. |

## Set up GitHub on your computer

### Option A: GitHub Desktop (recommended for new users)

1. Download and install [GitHub Desktop](https://desktop.github.com/).
2. Sign in using your NHS Wales GitHub account.
3. Open your repository page on GitHub.com.
4. Click the **Code** button and select **Open with GitHub Desktop**.
5. Choose a local folder and click **Clone**.

### Option B: Command line (for advanced users)

1. Ensure Git is installed: [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. On your repository page, click the **Code** button and copy the HTTPS or SSH URL.
3. Open a terminal and run:

```bash
git clone <repo-url>
cd <repo-name>
```

### Option C: Visual Studio or VS Code

1. Open Visual Studio or VS Code.
2. Use the **Clone Repository** option and paste the repository URL.
3. Sign in to GitHub when prompted to authenticate.

> **Further reading and information**
>
> [Setting up Git - GitHub Docs](https://docs.github.com/en/get-started/getting-started-with-git/set-up-git)
>
> [GitHub Desktop documentation](https://docs.github.com/en/desktop)

## First steps after getting access

Once you have access to a GitHub organisation:

1. **Complete your profile**: Add your full name and a profile photo to make collaboration easier.
2. **Enable two-factor authentication (2FA)**: This is **REQUIRED** for all NHS Wales GitHub accounts.
3. **Review the organisation's repositories**: Familiarise yourself with existing projects before creating new ones to avoid duplication.
4. **Read this handbook**: Understand the conventions and practices expected before starting work.

> **Practices to avoid**
>
> Do **NOT** use a personal GitHub account for NHS Wales work. Always use your NHS Wales
> GitHub account to ensure proper access control and audit trails.
>
> Do **NOT** store sensitive or patient-identifiable data in any GitHub repository. Use
> dummy or anonymised data in examples and tests.
