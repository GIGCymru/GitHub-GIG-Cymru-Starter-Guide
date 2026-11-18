# Managing Users, Teams and Permissions

## Add users to your organisation

Access to the GitHub GIG Cymru organisations is managed through NHS Wales Active Directory
via SSO. New users are provisioned through the IT service desk process described in
[Getting Started](getting-started.md).

When adding users to repositories or teams, you **MUST** grant only the minimum access level
necessary and follow the *principle of least privilege*.

> **Further reading and information**
>
> [Managing access to your organisation's repositories - GitHub Docs](https://docs.github.com/en/organisations/managing-user-access-to-your-organisations-repositories)

## Create and manage teams

Teams allow you to organise members and manage repository access at scale. Instead of granting
access to individuals, grant access to teams.

Each team **SHOULD** reflect a real-world working group (e.g. a product team, a component team,
or a platform team).

> **Practical tip**
>
> Use descriptive team names that reflect the team's focus. Avoid generic names like *"Developers"*.

> **Examples of good practice**
>
> `phoenix-portal-team` — Front-end UI and back-end API integration.
>
> `titan-mobile-team` — Mobile application development.
>
> `atlas-immunisations-api-team` — Backend immunisation APIs.
>
> `ndr-data-platform-team` — National Data Resource data platform.

### Recommended team permission levels for repositories

| **Team role** | **Recommended for** |
| --- | --- |
| **Read** | Stakeholders, QA reviewers with no code write access. |
| **Triage** | Issue managers and project coordinators. |
| **Write** | All active contributors (developers, analysts). |
| **Maintain** | Lead developers and team leads. |
| **Admin** | Repository owners only. |

> **Further reading and information**
>
> [Creating a team - GitHub Docs](https://docs.github.com/en/organisations/organising-members-into-teams/creating-a-team)

## Review and audit access

You **MUST** review repository and team access regularly to ensure it remains appropriate.

- Review access at least **quarterly**.
- Remove access **as soon as** a user leaves a project or organisation.
- Use the organisation's member audit log to track access changes.

> **Practices to avoid**
>
> Do **NOT** grant Admin access to all contributors. Admin access allows sensitive and
> destructive operations and **MUST** be reserved for repository owners.
>
> Do **NOT** use Personal Access Tokens (PATs) for service accounts unless there is no
> alternative. If PATs are used, set a short expiry (maximum 90 days) and rotate them regularly.

## Outside collaborators

Adding collaborators from outside your NHS Wales GitHub organisation requires approval from
the Organisation Owner. Outside collaborators **MUST NOT** be granted more than the minimum
access required for the specific task.

> **Further reading and information**
>
> [Adding outside collaborators to repositories - GitHub Docs](https://docs.github.com/en/organisations/managing-user-access-to-your-organisations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organisation)
