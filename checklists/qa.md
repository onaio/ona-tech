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
