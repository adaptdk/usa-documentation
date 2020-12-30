# New Project Checklist

Not every project is identical, so it's possible that not all of these items will be relevant to your project. Use your best judgement, and don't hesitate to ask the team if you have questions. Some of these tasks can be taken on by the PM if desired.

- [ ] Create Github team for project (see [documentation regarding team structure](../github-team-structure/README.md)). Set team access as needed.
- [ ] Create new Basecamp project.
  - [ ] Invite internal team members.
  - [ ] Invite client team members.
  - [ ] Add all relevant artifacts to the docs section in Basecamp.
- [ ] Create new Github repository.
- [Setup](https://help.github.com/en/articles/creating-a-pull-request-template-for-your-repository) the [pull request template](/issue-templates/Pull-Request-Template.md) in the project repository.
- [ ] Identify the project type, most likely *Scrum*, but use *Kanban* for maintenance projects.
- [ ] Setup the board to use.
  In most cases a Github project is enough, and in some complex cases Zenhub would work better.
  - [ ] Create a new Github Project, and setup status as columns.
  - [ ] Create a new Workspace in Zenhub, and setup status as pipelines.
  
  In either case status are a subset of the following.
  - New: Where issues go that have yet to be prioritized. Not needed on Github project.
  - Backlog: Issues move into the Backlog once they are assigned to a developer and are ready for implementation
  - In Progress: Issues that are currently being worked on
  - Review / QA: Catchall for code review and functional QA
  - Done: Merged into the main development branch, but not yet deployed to production
  - Closed: Deployed to production
  
  For a *Scrum* board: New, Backlog, In Progress, Review/QA, Closed.
  For a *Kanban* board: New, Backlog, In Progress, Review/QA, Done, Closed.
- [ ] Establish internal meeting cadence (aka standups) dependent on schedule + project size.
- [ ] Establish external meeting cadence with client
- [ ] Create Harvest project.
  - [ ] Add relevant team members.
- [ ] Schedule regular budget reviews
