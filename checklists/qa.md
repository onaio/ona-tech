What to look for when doing QA
---

Code is used MUCH MUCH MORE that it is written or read. When you are performing a quality assurance review on a feature branch or a product you are in the role of a user. User give expected and unexpected input, bad files, letter instead of numbers, clicking while loading, hitting the dreaded back button.

In feature QA, you have checked-out a branch and are checking that it is ready to merge into master

* [ ] Does the branch implement the new feature as described in the issue it closes?
* [ ] Does it do so without affecting existing functionality?

General QA

* [ ] Do input fields handle unexpected input? (E.g. if the fields expects number what happens when it gets alphaneumerics, what happens when it gets very long strings or no input at all?)
* [ ] Does the UI change to reflect expected updates? (E.g. when you delete something does a related counter decrement?)

WIP please add more!
