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
  you do. Provide them with as much context as you feel will be necessary for
  them to understand the changes you're proposing.
- A great way to provide context to the reviewer is to use Github's review
  features. For instance, if there is a line of code that you think will be
  confusing, comment inline on code in your own PR so that the reviewer will
  see it. You can find an [example of that in action](https://github.com/adaptdk/tufts-acsf/pull/335/files/fcfeee988c0082a24949cf18e66464fc518bc7e9#diff-8d31c81cc321d8731734e8da9e3af11a10306595cb94532b4d47c226582d9b32) on the Tufts ACSF project.
- Always provide thorough testing steps so that the reviewer can test appropriately. Testing steps include:
  - Any steps needed to get your environment into the state that should be tested
  - Any manual setup steps that need to happen prior to testing
  - Testing steps + expected outcomes

## Work in small batches

Whenever possible, favor small, frequently submitted batches of work over large infrequently submitted batches. Small batches of work are easier for a reviewer to reason about.

For instance, if you are assigned a ticket that will require changes to multiple parts of the system, consider submitting several PRs, one for each part of the system. This will allow the reviewer the opportunity to review each change in isolation, allowing them to provide better feedback.

Submitting small PRs early in the process also allows for early review from peers. For instance, if you aren't sure the best way to implement something, push up a WIP PR and ask for feedback from the team.

Keep in mind that `main` branch should always be in a deployable state. If you submit a PR that relies on work not yet complete, ensure that merging your initial PR will not bring `main` into a non-functional state. How to achieve this is a judgement call dependent on the situation, but usually their are logical boundaries which can be used to segment what goes into a PR. If needed you can always fall back to a single, larger PR utilizing the WIP PR state on Github to allow others the opportunity to review as you go.

## Reduce the number of hand-offs

Each hand-off requires context switching and communication, all of which take time. During a review, if you see something small that needs changing, feel free to make the change while reviewing the PR. If you do this, it's important that you make the change visible to the PR author so that they internalize your feedback and adjust their approach in the future. You can do this via Github's [suggested change feature](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request) or by commenting on the PR with a link to your relevant commit.

When to do this is a judgment call. In general, choose the route that will help the team progress the fastest. In other words, if you can eliminate the need for a hand-off by making a change yourself, this is usually the preferred option. On the other hand, if the needed change is large, intricate, or would provide useful context and learning opportunities for the dev, it's likely better to request changes from the original dev and incur the cost of the hand-off. In other words, it's a trade-off.

## Code reviews are for everyone

* If you are a team member on a project, request code reviews from a variety
  of team members.  This shares both the knowledge and the burden of the code
  review.
* If you are the team lead of a project and you are being asked to do a lot of
  code reviews, feel free to delegate reviews to other team members.  It is not
  only your responsibility to review code.  The team needs to see what others are
  doing and understand how or why it was done.

As much as possible we should share code reviews between the core team members.
Often, we default to requesting code reviews from the the project lead / architect,
but when the balance falls too far out of line, it takes up a large amount of time
for that person. This leads to lower quality review + fatigue on the architect.

Another benefit of sharing code review responsibilities is that domain knowledge
is spread out amongst team members. This helps prevent individual team members
from becoming single points of failure on a project.

## What to do when working solo

Occasionally you may be working on a project on your own.  Should you still go about
getting code reviews or should you merge straight to main?  Like so many other times,
the answer is "it depends".  If you are unsure if you should get a code review, review
the lists of examples below to help guide you.  If you are still unsure after reviewing the lists,
then it sounds like you may not be 100% confident in the change, in which case, ask for
a review!

_Note: Just remember that when you are working solo, it means that anyone you ask for a code
review will be taking time out of their allocations to review your code.  Before they get to
your PR and go 🤷, do that reviewer a solid by documenting your code, linking
to any relevant tickets, and writing a well formed PR summary with testing steps and notes about
pieces of the PR that may require context._

**Reasons you may not need a code review when working solo**

* The project has tests that cover the changed code and continue to pass
* The change is straightforward, such as copy change.
* The project is not yet live and the client is expecting to continue to refine
  the work.

**Reasons to seek code review when working solo**

* You want feedback on the code you've written, for example on whether
  there are better ways to solve the problem.
* You don't feel confident that you understand the code that you've changed
  or any potential side effects.
* You're working in a new project, language, framework, etc... and would like
  someone more experienced with that tool to approve the work.
* The change is large and touches many parts of the system.
* You want feedback on if the code is clear for future developers.
* The change is an important request and needs a second set of eyes to ensure
  correctness.
