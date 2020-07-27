This document defines the structure that all projects owned by Adapt USA should share. The goal is not to be rigid or overly prescriptive; individual projects can and should deviate from this structure as dictated by the project constraints. However, any deviation should be conscious and intentional.

This is a living document that will change as we learn and grow as an organization. Please submit pull requests liberally.

## Table of contents
* [Gathering Requirements](#gathering-requirements)
* [Project setup](#project-setup)
* [Sprint setup](#sprint-setup)
* [Ticketing workflow](#ticketing-workflow)
* [Development workflow](#development-workflow)
* [Time tracking](#time-tracking)
* [Client communication](#client-communication)
* [Tooling](#tooling)

## Gathering Requirements

This is a the first and arguably most critical part of the project life cycle. It is vital that we gather requirements precisely so that client expectations are lockstep with our own.

At the end of this phase, we should know the following:

* Broad context
  * What problem is the client facing?
  * How does this problem impact their business?
  * How has this problem been addressed in the past?
  * Who are the decision makers (stake holders) that we need to be aware of?
* Expectations
  * What is the desired end result (in detail)?
  * What is the project timeline?
  * What is driving the timeline?
  * What is the budget sensitivity?

Once detailed requirements are gathered from the client, they get recorded as one (or more) tickets in Github.

## Project setup

When we begin a new project, the following infrastructure needs to be established in order for our workflows to function:

* Create a new repository on GitHub under the `adaptdk` organization.
  * Set team access as needed.
* [Setup](https://help.github.com/en/articles/creating-a-pull-request-template-for-your-repository) the [pull request template](/issue-templates/Pull-Request-Template.md) in the project repository.
* Create a new Workspace in Zenhub
  * Ensure that the following Pipelines are in place:
    * New Issues: Where issues go that have yet to be prioritized
    * Backlog: Issues move into the Backlog once they are assigned to a developer and are ready for implemntation
    * In Progress: Issues that are currently being worked on
    * Review / QA: Catchall for code review and functional QA
    * Done: Merged into the main development branch, but not yet deployed to production
    * Closed: Deployed to production
* Create a new project in Basecamp & invite relevant team members (including client team members)
  * Add all relevant artifacts to the docs section in Basecamp
* Create a new project in Harvest and add relevant team members

## Milestone setup

We use milestones to organize our work. This is how milestones should be set up:

* Our preferred milestone length is 2 weeks.
  * For maintenance projects, it is acceptable not to create milestones. Maintenance projects typically do not have many active issues, so we do not need to open and close milestones needlessly.
* At the start of each milestone, the following tasks should be completed by the project lead / PM:
  * Create a deployment ticket to be used to track time spent on deployments, as well as any manual deployment steps specific to this deployment. Use [this template](/issue-templates/Deployment-Ticket-Template.md) for deployment tickets.
  * Assign an estimate to each ticket (in hours). This is used for planning purposes, as well as to set expectations with the assigned developer. Technically, Zenhub tracks estimates as story points, but we find these to be too vague for the context in which we operate.
  * Assign each ticket in the sprint to a developer based on that developers capacity & the estimates developed in the previous step.


## Ticketing workflow

Proper use of the ticketing system is especially important because we are a distributed team with different working hours.

Developers should treat the comment section of a ticket as historical record. It's important for us to have a history of the thinking, rationale, and context behind each issue. This will be helpful to us in the future if we ever need to figure out why we did something a certain way. It will also help us to maintain transparency with the client and among our own team members. As a developer decides on high level implementation details, they should be recorded in the ticket.

Each ticket should be assigned an estimate (in hours) by the project lead before it is assigned for implementation. **Important:** if the developer working the ticket does not agree with the estimate, it is their responsibility to communicate this to the project lead. In addition, if it becomes clear that the task will take longer than estimated, the implementing developer **must** socialize this to the project leader.

Tickets in the active sprint are organized into pipelines. Those are:
  * Backlog: Where tickets sit that have not been started yet
  * In Progress: Actively being worked on by a developer
  * Review / QA: Catch all for code review + internal QA
  * Done: Merged into develop branch, but not yet deployed to production
  * Closed: Deployed to production

## Development workflow

Our development workflow centers around the [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). You should be familiar with the general concepts before reading further.

* When a developer begins working on a ticket, they first move it from the `Backlog` column into the `In Progress` column. This gives everyone on the team insight into the current state of the sprint.
* Any and all communication related to a ticket should be entered in the comment section for that ticket. Keeping communication organized is vital to our success.
* If there are manual deployment steps, these should be documented in the ticket and the lead developer should be tagged (via @). The project lead should then move the manual deployment steps into the deployment ticket for that sprint.
* Once the developer is finished with a ticket, she:
  * Moves the ticket into the `Review / QA` column
  * Creates a pull request (PR) against the `develop` branch
  * Fills out the PR template in Github
  * Assigns the PR to the project lead in Github
  * Connects the PR with the ticket via Zenhub's UI
* Project lead conducts code review + QA. Any and all feedback related to a PR is done in GitHub using the built-in review tools.
* If the issue needs further work, the PR is assigned back to the developer, and the ticket is moved back into `In Progress`. This cycle repeats until the PR is merged to develop
* Once PR is merged to develop, project lead moves the ticket into the `Done` column
* On the last day of the milestone, the work from that was completed in the milestone is deployed to production.

## Time tracking

* All time should be logged to a specific ticket in Harvest.
* It is recommended to use the [Harvest plugin for chrome](https://chrome.google.com/webstore/detail/harvest-time-tracker/fbpiglieekigmkeebmeohkelfpjjlaia?hl=en) to make time tracking easier (Firefox equivalent looks to exist)

## Client communication

* We strive to make client communication as visible as possible to everyone involved in the project. This communication is a historical record that we can use to justify our actions + decision making.
* As much as possible, we should be conducting client communication in Basecamp
* Non technical clients should not be granted access to Github
* Technical clients that prefer a more hands on approach can be granted Github access if needed

## Tooling

- Git repo: Github
- Ticketing: Github
- Time tracking: Harvest
- Client communication: Basecamp