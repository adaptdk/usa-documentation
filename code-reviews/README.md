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

## Democratize code review

As much as possible we should share code reviews between the core team members.
This task falls to the project lead / architect by default, but when the
balance falls too far out of line, it takes up a large amount of time for that
person. This leads to lower quality review + fatigue on the architect.

Another benefit of sharing code review responsibilities is that domain knwoledge
is spread out amongst team members. This helps prevent individual team members
from becoming single points of failure on a project.
