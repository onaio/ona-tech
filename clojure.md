## Clojure

* [http://java.ociweb.com/mark/clojure/article.html](http://java.ociweb.com/mark/clojure/article.html)


## Midje Testing Library Documentation
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
