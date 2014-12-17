What to look for when doing a code review
---

Code is read MUCH MUCH MORE than it is written. When you are reviewing code, you are not just helping the author make sure that they wrote code that solves an issue correctly. You are helping ensure that the code they wrote is easy to **read** and maintain over the long term, and is thoroughly devoid of ["code smell"](http://en.wikipedia.org/wiki/Code_smell).

A brief "checklist" that may be helpful to go through in a code review
 * [ ] Solves the problem (test it), including appropriate edge cases.
 * [ ] Code is written following the appropriate style guide for the language.
 * [ ] Code is tested as appropriate. Tests are a must have in general, but particularly so for regressions. [1]
 * [ ] DRY (Don't Repeat Yourself).
 * [ ] Related: if multiple similar problems are being solved, can abstractions be created? Note: 1 use case does not an abtraction merit; premature abstractions are problematic as well.
 * [ ] Documentation: do all new functions have docstrings? Are docstrings modified if they need to be? Outdated documentation is worse than no documentation, which is much worse than [good](https://github.com/onaio/ona-tech/blob/master/checklists/docs.md) and up to date documentation.

The checklist of smells taken directly from the ["code smell"](http://en.wikipedia.org/wiki/Code_smell) document

* [ ] Duplicated code: identical or very similar code exists in more than one location.
* [ ] Long method: a method, function, or procedure that has grown too large.
* [ ] Large class: a class that has grown too large. See God object.
* [ ] Too many parameters: a long list of parameters is hard to read, and makes calling and testing the function complicated. It may indicate that the purpose of the function is ill-conceived and that the code should be refactored so responsibility is assigned in a more clean-cut way.
* [ ] Feature envy: a class that uses methods of another class excessively.
* [ ] Inappropriate intimacy: a class that has dependencies on implementation details of another class.
* [ ] Refused bequest: a class that overrides a method of a base class in such a way that the contract of the base class is not honored by the derived class. See Liskov substitution principle.
* [ ] Lazy class / Freeloader: a class that does too little.
* [ ] Contrived complexity: forced usage of overly complicated design patterns where simpler design would suffice.
* [ ] Excessively long identifiers: in particular, the use of naming conventions to provide disambiguation that should be implicit in the software architecture.
* [ ] Excessively short identifiers: the name of a variable should reflect its function unless the function is obvious.
* [ ] Excessive use of literals: these should be coded as named constants, to improve readability and to avoid programming errors. Additionally, literals can and should be externalized into resource files/scripts where possible, to facilitate localization of software if it is intended to be deployed in different regions.
* [ ] Cyclomatic complexity: too many branches or loops; this may indicate a function needs to be broken up into smaller functions, or that it has potential for simplification.
* [ ] Downcasting: a type cast which breaks the abstraction model; the abstraction may have to be refactored or eliminated.[5]

[1] - The one exception is if we haven't solved *how* to test certain things yet. Eg. asynchronous tests in CLJS were not figured out in Zebra by Dec 2014.
