What to look for when doing a code review.
---

Code is read MUCH MUCH MORE than it is written. When you are reviweing code, you are not just helping the author make sure that she wrote code that solves an issue correctly. You are helping ensure that the code she wrote is easy to **read** and maintain over the long term, and is thoroughly devoid of ["code smell"](http://en.wikipedia.org/wiki/Code_smell).

A brief "checklist" that may be helpful to go through in a code review
 * [ ] Solves the problem (test it), including appropriate edge cases.
 * [ ] Code is written following the appropriate style guide for the language.
 * [ ] Code is tested as appropriate. Tests are a must have in general, but particularly so for regressions. [1]
 * [ ] DRY (Don't Repeat Yourself).
 * [ ] Related: if multiple similar problems are being solved, can abstractions be created? Note: 1 use case does not an abtraction merit; premature abstractions are problematic as well.
 * [ ] Documentation: do all new functions have docstrings? Are docstrings modified if they need to be? Outdated documentation is worse than no documentation, which is much worse than good and up to date documentation.

[1] - The one exception is if we haven't solved *how* to test certain things yet. Eg. asynchronous tests in CLJS were not figured out in Zebra by Dec 2014.
