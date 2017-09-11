## This wiki describes the quality assurance process to QE pull requests and production releases.

#### Terms used

1. QE - Quality Engineering
2. CR - Code Review
3. QA - Quality Assurance
4. PR - Pull Request

#### Steps to QE a Pull Request
 
1. Issues are logged by team members on github and picked up by a developer.
  * Issues may be verified by an additional team member to verify the acceptance criteria that will deem the issue as passed.
  * If there is a Intercom or HelpScout ticket related to the issue, put a link to the Intercom/HelpScout ticket into the issue and paste in the support email.
2. Once fixed, developer adds the label `Has - PR` and moved to pull requests.
3. Peer code review of the fixed issue is run and if this passes, the label `CR+` is applied to the PR.
  * If this fails, the label `CR-` is applied to the PR. In this case, the issue does not go on to QA.
4. Once a PR has passed code review, check that the PR has been built successfully.
  * If the build fails, this PR does not go on to QA.
5. Thereafter, QA and developer who opened the PR should then have a hand-off on Slack. A summary of this conversation is then logged to the PR on github. This will serve as history to the issue.
6. QA will setup the feature branch on either their local machine, staging, or preview
7. QA will then run functionality tests on passed issues in the pull requests and apply the label `QE+` if functionality has passed. If the issue fails, QA will apply the label `QE-` and assign back to the developer.
8. When tests are complete, a merge is initiated by QA.

#### Steps to QE a Production Release

1. For release management, tag the release with the next release number and compare changes to list out the differences in the current and previous release.
2. DevOps will at this point deploy a release to preview and staging.
3. QA will then perform a test run on the release and this includes cross browser tests, mobile tests and where deemed necessary, (by either the developer or QA) [regression tests](https://docs.google.com/spreadsheets/d/1f5hlQBiAZ8fBFZ_rRaJ1wmwaufYXLFuLK46fNyYZQKM/edit#gid=2054763193). 

#### Steps to Push a Release to Production
4. Make an internal announcement to everyone (`@channel`) on the `#general` and `#qa` channels, linking to the release notes.
5. Create public release notes based on the private release notes and add to the [release notes](https://ona.io/release-notes.html) page.
  * This will not include issue numbers, non-functional changes.
  * This will be dated.

#### Appendix

* [Zebra](http://drone.onalabs.org/onaio/zebra) is built on Drone
* [Core](https://travis-ci.com/onaio/core) is built on Travis Magnum
* Our open source libraries ([Hatti](https://travis-ci.org/onaio/hatti/), [Milia](https://travis-ci.org/onaio/milia/), [Vega Viewer](https://travis-ci.org/onaio/vega-viewer/)) are built on Travis
* As soon as possible we will begin automating the regression tests through integration tests using Selenium (or equivalent)

What to look for when doing QA
---

Code is used much much more that it is written or read. When you are performing a quality assurance review on a feature branch or a product you are in the role of a user. Users give expected and unexpected input, bad files, letters instead of numbers, clicking while loading, hitting the dreaded back button, etc.

In feature QA, you have checked-out a branch and are checking that it is ready to merge into master

* [ ] Does the branch implement the new feature as described in the issue it closes?
* [ ] Does it do so without affecting existing functionality?

General QA

* [ ] Do input fields handle unexpected input? (E.g. if the field expects numbers what happens when it gets alphanumerics, what happens when it gets very long strings or no input at all?)
* [ ] Does the UI change to reflect expected updates? (E.g. when you delete something does a related counter decrement?)

How To use the [#qa](https://onaio.slack.com/messages/qa/) channel
---

This channel is specifically for *request* QA and *responding* to QA requests, that's it.

Did QA lead to other issues or ideas for features? Is the issue description unclear or does performance seem like it's lagging while you do QA? Dicuss on the project's channel.

How a QAing flow happens via this channel:

> `rr:` "@carolyn @jmunene @sm @roger can you please QA https://github.com/onaio/zebra/issues/1337 it’s on stage”

> `jmunene:` "OK, I'm on it"

> `jmunene:` "1337 passed QA" 

or, much less likely:

> `jmunene:` "1337 failed QA, downloaded forms are still blank, try with this [link to a page with a download XLS form button]" 

If a problem is found, you should call it out and mark it in the [QA document](https://docs.google.com/spreadsheets/d/1f5hlQBiAZ8fBFZ_rRaJ1wmwaufYXLFuLK46fNyYZQKM/edit). Also, reopen the issue with details of the problem, put it in the current milestone, and ping the person who was assigned. If the problem blocks deploy, mark it in the "Blocker" column.

