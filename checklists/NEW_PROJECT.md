# New Project Checklist

Not every project is identical, so it's possible that not all of these items will be relevant to your project. Use your best judgement, and don't hesitate to ask the team if you have questions. Some of these tasks can be taken on by the PM if desired.


- [ ] Create new Github repository.
  - [ ] Change settings to remove branches after merges.
- [Setup](https://help.github.com/en/articles/creating-a-pull-request-template-for-your-repository) the [pull request template](/issue-templates/Pull-Request-Template.md) in the project repository.
- [ ] Identify the project type, most likely *Scrum*, but use *Kanban* for maintenance projects.
- [ ] Setup the board to use.
  - [ ] Create a new Workspace in Zenhub, and setup status as pipelines.

  Status's are a subset of the following:
  - New: Where issues go that have yet to be prioritized.
  - Backlog: Issues move into the Backlog once they are ready for implementation
  - In Progress: Issues that are currently being worked on
  - Review / QA: Catchall for code review and functional QA
  - Done: Merged into the main development branch, but not yet deployed to production
  - Closed: Deployed to production

  For a *Scrum* board: New, Backlog, In Progress, Review/QA, Closed.
  For a *Kanban* board: New, Backlog, In Progress, Review/QA, Done, Closed.
  
- [ ] Add the following github teams to the project repo (see [documentation regarding team structure](../github-team-structure/README.md))
  - [ ] [adapt-usa-admin](https://github.com/orgs/adaptdk/teams/adapt-usa-admin) should have admin access
  - [ ] [adapt-usa-developers](https://github.com/orgs/adaptdk/teams/adapt-usa-developers) should have write access
  - [ ] [adapt-usa-pm](https://github.com/orgs/adaptdk/teams/adapt-usa-pm) should have maintain access
- [ ] Create new Basecamp project.
  - [ ] Invite internal team members.
  - [ ] Invite client team members.
  - [ ] Add all relevant artifacts to the docs section in Basecamp.
- [ ] Establish internal meeting cadence (aka standups) dependent on schedule + project size.
- [ ] Establish external meeting cadence with client
- [ ] Schedule regular budget reviews
- [ ] Write "Project Kickoff" document based on [this template](https://3.basecamp.com/4276003/buckets/13508696/messages/4367357594) and post to Basecamp so that onboarding team members is smoother
  - What problem are we solving / what is the intended end goal?
  - Who are the key stakeholders on the client team and what are their roles?
  - Summary of what we know so far
  - Access
  - Artifacts
