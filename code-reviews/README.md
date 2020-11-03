# Code Reviews

## For the reviewer

- Avoid judgement - assume that everyone is intelligent and well meaning.
- Ask questions and get clarifications. These may spark new ideas for the
  developer that has opened the pull request and help you understand why a
  change is happening.
- Find something positive to say about the work you're reviewing, especially if
  you have some changes to request. People are more receptive to feedback if
  you can frame the discussion positively.

## Having your code reviewed

- Remember that the person reviewing your work does not have as much context as
  you do. Provide them with as much context as you feel will be nessicary for
  them to understand the changes you're proposing.
- A great way to provide context to the reviewer is to use Github's review
  features. For instance, if there is a line of code that you think will be
  confusing, comment inline on code in your own PR so that the reviewer will
  see it. You can find an [example of that in action](https://github.com/adaptdk/tufts-acsf/pull/335/files/fcfeee988c0082a24949cf18e66464fc518bc7e9#diff-8d31c81cc321d8731734e8da9e3af11a10306595cb94532b4d47c226582d9b32) on the Tufts ACSF proeject.
- Always provide thorough testing steps so that the reviewer can test appropriately. Testing steps include:
  - Any steps needed to get your environment into the state that should be tested
  - Any manual setup setps that need to happen prior to testing
  - Testing steps + expected outcomes

## Work in small batches

Whenever possible, favor small, frequently submitted batches of work over large infrequently submitted batches. Small batches of work are easier for a reviewer to reason about.

For instance, if you are assigned a ticket that will require changes to multiple parts of the system, consider submitting several PRs, one for each part of the system. This will allow the reviwer the opportunity to review each change in isolation, allowing them to provide better feedback.

Submitting small PRs early in the process also allows for early review from peers. For instance, if you aren't sure the best way to implement something, push up a WIP PR and ask for feedback from the team.

Keep in mind that `main` branch should always be in a deployable state. If you submit a PR that relies on work not yet complete, ensure that merging your initial PR will not bring `main` into a non-functional state. How to acheive this is a judgement call dependent on the situation, but usually their are logical boundaries which can be used to segment what goes into a PR. If needed you can always fall back to a single, larger PR utilizing the WIP PR state on Github to allow others the opportunity to review as you go.

## Democratize code review

As much as possible we should share code reviews between the core team members.
This task falls to the project lead / architect by default, but when the
balance falls too far out of line, it takes up a large amount of time for that
person. This leads to lower quality review + fatigue on the architect.

Another benefit of sharing code review responsibilities is that domain knwoledge
is spread out amongst team members. This helps prevent individual team members
from becoming single points of failure on a project.
