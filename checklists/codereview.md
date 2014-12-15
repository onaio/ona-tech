What to look for when doing a code review.
---

Code is read MUCH MUCH MORE than it is read. When you are looking at code for a code review, you are helping the author make sure that she / he wrote the correct code. You are helping think of edge cases that they didn't think of. But most importantly, you are making sure that code quality is high, that the code doesn't ["smell"](http://en.wikipedia.org/wiki/Code_smell).

A brief "checklist" that may be helpful to go through in a code review
 * [ ] Code is written following the appropriate style guide for the language.
 * [ ] Code is tested as appropriate. For regressions, tests are a must have [1].
 * [ ] DRY (Don't Repeat Yourself).
 * [ ] Related: if multiple similar problems are being solved, can abstractions be created? Note: 1 use case does not an abtraction merit. Premature abstraction can be problematic as well.
 * [ ] Documentation: do all new functions have docstrings? Are docstrings modified if they need to be? Outdated documentation is worse than no documentation, which is much worse than good and up to date documentation.

[1] - The one exception is if we haven't solved *how* to test certain things yet. eg. asynchronous tests in cljs were not figured out in Zebra by Dec 2014.
