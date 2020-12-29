# Github Team Organization

Repository access is managed via Github's Team feature.

## Adapt USA Team Structure

- [Adapt USA](https://github.com/orgs/adaptdk/teams/adapt-usa/members): Top level team. All team members should belong to this group (including contractors). It grants access to relatively insensitive material. This group should not be given access to client repositories.
- [Adapt USA Admin](https://github.com/orgs/adaptdk/teams/adapt-usa-admin): This a small group of trusted team members. This group should be given admin permission on all new repositories.
- [Adapt USA Developers](https://github.com/orgs/adaptdk/teams/adapt-usa-developers): This group should be given write access on new repos. Only FTE's should belong to this group.
- [Adapt USA PM](https://github.com/orgs/adaptdk/teams/adapt-usa-pm): This group should be given maintain access on all new repos.
- Project Specific Team: Project specific teams should be used to grant contractors or other non-FTE team members repository access. Their access should be tightly scoped to the project at hand.

## Client Projects

Access to client project repositories should be granted via a sub-group specific to that client. This team should be a child of `Adapt USA` team to keep organization clean. Only team members actively working on the project should be granted access to this team.

## Restricting Repository Access

In some projects, it may be good to protect the `main` branch by enabling [branch restrictions](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/enabling-branch-restrictions). In this case, ensure that you grant access to `main` via a group. This could be an existing group (ex. Adapt USA Developers), or a new project specific group. Use your best judgment to make this decision.
