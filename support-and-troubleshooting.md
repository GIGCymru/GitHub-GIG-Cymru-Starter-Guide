# Support and Troubleshooting

## Getting help

If you need help with GitHub GIG Cymru, use the following escalation path:

| **Issue type** | **Where to get help** |
| --- | --- |
| Access requests (new users, new repositories) | Your local IT service desk |
| Licensing requests (Codespaces, Copilot, GHAS) | Your local budget holder, then IT service desk |
| Organisation-level configuration | GitHub GIG Cymru service team |
| General GitHub usage questions | [GitHub Docs](https://docs.github.com/) or peer support via your team |
| NHS Wales information governance | [DHCW Information Governance](https://dhcw.nhs.wales/information-governance/) |

## Frequently asked questions

### General

**Q: What is GitHub GIG Cymru?**

A: GitHub GIG Cymru is a managed GitHub Enterprise platform provided for NHS Wales
organisations. It enables secure, collaborative software development and knowledge sharing
across NHS Wales, hosted under the [GIGCymru GitHub organisation](https://github.com/GIGCymru).

**Q: Who can use GitHub GIG Cymru?**

A: All NHS Wales organisations can request access via their local IT service desk. The service
is expanding, with a vision to include all NHS Wales and social care organisations.

**Q: Can I use my personal GitHub account for NHS Wales work?**

A: No. You **MUST** use your NHS Wales GitHub account for all NHS Wales work to ensure proper
access control and audit trails.

### Access

**Q: How do I request access?**

A: Contact your local IT service desk and request access to GitHub GIG Cymru. Specify which
GitHub organisation you need access to.

**Q: How do I get access to Codespaces or Copilot?**

A: These features require additional licensing. Contact your local budget holder for approval
before submitting a request to the GitHub GIG Cymru service team.

**Q: I've lost access to my repository — what do I do?**

A: Contact your repository's Organisation Owner or your local IT service desk. Do not attempt
to create a new account to bypass access controls.

### Repositories

**Q: How do I share code with colleagues in other NHS Wales organisations?**

A: Set your repository visibility to `Internal`. This makes it accessible to all members of
the GitHub Enterprise across NHS Wales organisations without making it public.

**Q: Can I make my repository public?**

A: Only with explicit approval. Contact the GitHub GIG Cymru service team before making any
repository public. All source code is private by default.

**Q: What should I do if I accidentally commit a secret or sensitive data?**

A: Immediately revoke or change the exposed credential. Then contact the GitHub GIG Cymru
service team for assistance removing the data from the repository history. Report the incident
through your organisation's information security incident process.

### GitHub Actions

**Q: My GitHub Actions workflow is failing — where do I start?**

A: Check the workflow run logs in the **Actions** tab of your repository. Common causes include:
missing or expired secrets, pinned action versions being unavailable, and failed status checks.

**Q: Can I use self-hosted runners?**

A: Yes, but self-hosted runners **MUST** be approved by the GitHub GIG Cymru service team
and **MUST** comply with NHS Wales security standards. Contact the service team before
configuring self-hosted runners.

### Azure DevOps integration

**Q: Can I use GitHub and Azure DevOps together?**

A: Yes. See [Integrating with Azure DevOps](integrating-with-azure-devops.md) for guidance
on the recommended integration patterns.

**Q: Should I use GitHub Actions or Azure Pipelines?**

A: For repositories hosted in GitHub, GitHub Actions is **RECOMMENDED** for CI. Azure
Pipelines may be more appropriate for CD to Azure-hosted services or for cross-platform
deployments. See [Integrating with Azure DevOps](integrating-with-azure-devops.md) for more detail.

## Training and further resources

| **Resource** | **Link** |
| --- | --- |
| GitHub Skills (interactive learning) | [https://skills.github.com/](https://skills.github.com/) |
| GitHub Foundations certification | [Microsoft Learn](https://learn.microsoft.com/en-gb/collections/o1njfe825p602p) |
| GitHub Docs | [https://docs.github.com/](https://docs.github.com/) |
| DHCW Software Engineering Handbook | [https://gigcymru.github.io/dhcw-software-engineering-handbook/](https://gigcymru.github.io/dhcw-software-engineering-handbook/) |
| Azure DevOps Handbook | [https://gigcymru.github.io/dhcw-software-engineering-handbook/azure-devops-handbook/introduction/](https://gigcymru.github.io/dhcw-software-engineering-handbook/azure-devops-handbook/introduction/) |
