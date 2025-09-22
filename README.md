
# GitHub GIG Cymru Quickstart Guide

Welcome to **GitHub GIG Cymru** – the NHS Wales national GitHub Enterprise solution! This guide will help you get started, understand the benefits, and adopt best practices for collaborative development.

---

## What is GitHub GIG Cymru?

GitHub GIG Cymru is a secure, centrally managed GitHub Enterprise platform provided by NHS Wales. It enables organisations to:

- **Develop under a community umbrella:** Each organisation gets its own GitHub organisation, fostering collaboration and knowledge sharing across NHS Wales.
- **Leverage enterprise features:** Benefit from advanced security, compliance, and management tools.
- **Collaborate securely:** Work with colleagues across NHS Wales in a trusted environment.
- **Accelerate digital transformation:** Share code, automate workflows, and build solutions together.

---

## Getting Started with GitHub

### 1. Sign Up and Access

1. Visit [https://github.com](https://github.com) and sign in with your NHS Wales credentials (if SSO is enabled). 
2. Request access to your [https://github.com/GIGCymru] (organisation’s GitHub org) via your local service desk. 

### 2. Create a New Repository

1. Go to your organisation’s page (e.g., `https://github.com/DHCW-Digital-Health-and-Care-Wales`).
2. Click **New repository**.
3. Fill in the repository name, description, and choose visibility (private/public as appropriate).
4. Click **Create repository**.

### 3. Set Up the Repository on Your Computer

#### Option A: Using GitHub Desktop (Recommended for new users)

1. Download and install [GitHub Desktop](https://desktop.github.com/) if you haven't already.
2. Sign in to GitHub Desktop with your NHS Wales GitHub account.
3. On your repository page, click the **Code** button and select **Open with GitHub Desktop**.
4. Choose where to save the repository on your computer and click **Clone**.
5. GitHub Desktop will download the repository and you can start working with your files.

#### Option B: Using Command Line (For Advanced Users)

1. On your repo page, click the **Code** button and copy the HTTPS URL.
2. Open a terminal and run:
	```bash
	git clone <repo-url>
	```
3. Change into the repo directory:
	```bash
	cd <repo-name>
	```

### 4. Using GitHub Codespaces

1. On your repo page, click the **Code** button and select **Codespaces** > **Create codespace on main**.
2. This launches a cloud-based development environment in your browser.

### 5. Using Visual Studio or VS Code

1. Open Visual Studio or VS Code.
2. Use the **Clone Repository** feature and paste your repo URL.
3. Start coding and commit changes directly from your IDE.

---

## Branching and Best Practices

### What is Branching?

Branching lets you work on new features or fixes without affecting the main codebase. The `main` branch is usually the stable, production-ready branch.

### Creating a Branch

#### Using GitHub Desktop:
1. In GitHub Desktop, click **Current Branch** at the top.
2. Click **New Branch**.
3. Give your branch a meaningful name (e.g., "feature/data-analysis" or "update/report-template").
4. Click **Create Branch**.

#### Using Command Line:
```bash
git checkout -b feature/my-new-feature
```

### Best Practices

- **Use meaningful branch names:** e.g., `analysis/patient-outcomes`, `report/monthly-dashboard`, `fix/data-import-error`.
- **Keep branches focused:** One analysis, report, or fix per branch.
- **Regularly sync with main branch:**
  - **In GitHub Desktop:** Click **Fetch origin** regularly, then **Pull origin** if there are updates.
  - **In Command Line:**
    ```bash
    git checkout main
    git pull
    git checkout your-branch-name
    git merge main
    ```
- **Commit your work regularly:**
  - **In GitHub Desktop:** Review your changes, add a summary message, and click **Commit**.
  - Write clear commit messages like "Add patient satisfaction analysis" or "Fix data filtering issue".
- **Open Pull Requests (PRs):** When your work is ready, open a PR for review and feedback.
- **Delete branches after merging:** Keeps the repository organised.

---

## Common Workflows

### Making Your First Changes

1. **Open your files:** Navigate to your repository folder on your computer and open files in your preferred editor (Excel, R Studio, Python IDE, etc.).
2. **Make changes:** Edit your analysis files, add new reports, or update documentation.
3. **Review changes in GitHub Desktop:**
   - Open GitHub Desktop
   - You'll see your changed files listed
   - Click on a file to see what changed (green = added, red = removed)
4. **Commit your changes:**
   - Add a summary like "Update patient data analysis"
   - Optionally add a description for more details
   - Click **Commit to [branch-name]**
5. **Share your work:**
   - Click **Push origin** to upload your changes to GitHub
   - Your colleagues can now see your work online

### Collaborating with Colleagues

1. **Stay up to date:** Click **Fetch origin** regularly to see if colleagues have made changes.
2. **Create a Pull Request:**
   - When your analysis is ready for review, click **Create Pull Request** in GitHub Desktop
   - Or go to GitHub.com, navigate to your repository, and click **New Pull Request**
   - Add a description of what you've done
   - Request reviews from colleagues
3. **Respond to feedback:** Make any requested changes and push them to the same branch.

### Working with Data Files

- **Large files:** For files over 100MB, consider using Git LFS (Large File Storage) or cloud storage links
- **Sensitive data:** Never commit personal or sensitive data directly. Use sample/dummy data for code examples
- **File formats:** Git works best with text files (.py, .R, .sql, .md), but can handle binary files (.xlsx, .pdf) too

---

## Need Help?


Happy coding under the NHS Wales community umbrella!

---

# GitHub GIG Cymru FAQ

## General Information
**Q: What is GitHub GIG Cymru?**  
A: GitHub GIG Cymru is a managed service provided by NHS Wales through the GitHub Enterprise platform. It offers each NHS Wales organisation a collaborative space to facilitate cross-organisational development and knowledge sharing. Future expansions aim to include social care organisations as well.

**Q: Who can use GitHub GIG Cymru?**  
A: All NHS Wales organisations can request access via their local IT service desk. The service is expanding, with a vision to include all NHS Wales and social care organisations.

**Q: What is the vision for GitHub GIG Cymru?**  
A: To foster innovation and collaboration among data science teams, leveraging advanced technologies and skills. GitHub GIG Cymru enables projects that span organisational borders, empowering users to drive progress in health and care.

## Access
**Q: How do I get access?**  
A: Contact your local IT service desk for initial setup and access requests.

**Q: How do I get access to Codespaces or Copilot?**  
A: Some features like Codespaces or Copilot may require additional licensing. Contact your local budget holder for permission before requesting acccess.

## Training and Resources
**Q: What training is available?**  
A: Training resources include:
- [GitHub Help Documentation](https://docs.github.com/)
- [GitHub GIG Cymru Documentation](https://github.com/GIGCymru/)
- Community forums and peer support

**Q: How do I access shared resources?**  
A: Join relevant repositories or use GitHub’s search to find shared resources within your organisation.

## Collaboration and Best Practices
**Q: How do I share code with colleagues and other organisations?**  
A: Create a repository in your organisational GitHub space and set its visibility to "Internal" or invite collaborators directly.

**Q: How do I know if I am following coding best practice?**  
A: Use pull requests for code review, follow your organisation’s coding standards, and document shared procedures in your repo.

**Q: What if my organisation has different standards?**  
A: Communicate and align on shared standards before collaborating. Use repository documentation to record agreed practices.

## Features of GitHub GIG Cymru
GitHub GIG Cymru offers:
- **Private & Internal Repositories:** Securely host and manage code.
- **Team Management:** Control access and permissions.
- **Code Review:** Use pull requests to maintain code quality.
- **Project Management:** Track tasks and issues with GitHub Projects.
- **Actions:** Automate workflows with GitHub Actions (CI/CD).
- **Security:** Advanced features like dependency and secret scanning.
- **Insights & Analytics:** Monitor project activity and team performance.
- **AI-Assisted Programming:** Use GitHub Copilot (where licensed).
- **Cloud Development:** Use Codespaces for consistent, cloud-based dev environments.

## Security and Compliance
**Q: How is our data kept secure?**  
A: GitHub Enterprise provides robust security, including encryption, access controls, and vulnerability monitoring. NHS Wales enforces additional compliance and all users are authenticated via NHS Wales Active Directory.

**Q: Are there compliance requirements?**  
A: Yes, all users must comply with NHS Wales data protection, privacy, and information security policies.

**Q: How does GitHub GIG Cymru support DHCW’s strategic goals?**  
A: It enables digital transformation, supports high-quality digital products, expands digital health records, drives innovation, and aligns with IT service management best practices.

## Additional Features and Benefits
GitHub GIG Cymru supports a wide range of projects, including:
- Cross-organisation collaboration
- Open source initiatives
- Big data, machine learning, and research
- Proof of concept and hackathons
- Infrastructure deployment

Advanced features include version control, project discussions, issue tracking, CI/CD, and more. Some features may require additional licensing.

---

For the latest information, always refer to the [GitHub GIG Cymru Documentation](https://github.com/GIGCymru/) or contact your local IT service desk.
