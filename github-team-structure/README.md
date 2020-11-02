# Github Team Organizaion

Repository access is managed via Github's Team feature.

## Adapt USA

We have an overarching team, called [Adapt USA](https://github.com/orgs/adaptdk/teams/adapt-usa/members). All team members that work with
the US team should belong to this group (including contractors). It grants
access to relatively insensitive material, shuch as this documentation wiki. This
group should not be given access to client repositories.

## Client Projects

Access to client project repositories should be granted via a sub-group specific to that client. This team should be a child of `Adapt USA` team to keep organization clean. Only team members actively working on the project should be granted access to this team.

## Restricting Repository Access

In some projects, it may be good to protect the `main` branch by enabling [branch restrictions](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/enabling-branch-restrictions). If this strategy is used, create a second nested team that further restricts the client specfic team to a set of trusted administrators. This setup makes the most sense when working with collaborators that are not yet trusted team members.
