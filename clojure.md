## Clojure

* [Clojure - Functional Programming for the JVM](http://java.ociweb.com/mark/clojure/article.html)
* [Clojure for the Brave](http://www.braveclojure.com/) - good intro to Clojure
  * The chapters on macros are great: [Read, Eval, and Macros](http://www.braveclojure.com/read-and-eval/), and [Writing Macros](http://www.braveclojure.com/writing-macros/)
* [O'Reilly's Clojure Cookbook](https://github.com/clojure-cookbook/clojure-cookbook)
* [Clojure Destructuring Tutorial and Cheat Sheet](https://gist.github.com/john2x/e1dca953548bfdfb9844)
* [Clojure cheatsheet](http://clojure.org/cheatsheet)

### Libraries
* [Enlive - Clojure templating](https://github.com/cgrand/enlive) - used in Zebra
* [Tower](https://github.com/ptaoussanis/tower) is a Clojure i18n & L10n library.

### Midje Testing Library Documentation
To import the testing library to a test suite:
`(:use midje.sweet)`

To run tests do `lein midje`

Test case example:
```
(facts "about `first-element`"
  (fact "it normally returns the first element"
    (first-element [1 2 3] :default) => 1
    (first-element '(1 2 3) :default) => 1)
```

Midje also has autotest functionality that runs all the tests and then watches for changes to the source and test directories. When a file changes, it reloads the changed file and files that depend on it.

Ref: [Midje Testing Tutorial](https://github.com/marick/Midje/wiki/A-tutorial-introduction)
