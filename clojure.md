## Clojure

* [Learning Clojure](https://github.com/boston-clojure/learning-clojure) - learning and teaching links
* [Clojure - Functional Programming for the JVM](http://java.ociweb.com/mark/clojure/article.html)
* [Clojure for the Brave](http://www.braveclojure.com/) - good intro to Clojure
  * The chapters on macros are great: [Read, Eval, and Macros](http://www.braveclojure.com/read-and-eval/), and [Writing Macros](http://www.braveclojure.com/writing-macros/)
* [O'Reilly's Clojure Cookbook](https://github.com/clojure-cookbook/clojure-cookbook)
* [Joy of Clojure](http://www.joyofclojure.com/toc/index.html)

### Cheatsheets:
* [Clojure Destructuring Tutorial and Cheat Sheet](https://gist.github.com/john2x/e1dca953548bfdfb9844)
* [Clojure cheatsheet](http://clojure.org/cheatsheet)

### Articles:
* [Polymorphism in clojure](http://blog.8thlight.com/myles-megyesi/2012/04/26/polymorphism-in-clojure.html)

### Libraries
* [Enlive - Clojure templating](https://github.com/cgrand/enlive) - used in Zebra
* [Hiccup](https://github.com/weavejester/hiccup) - html representation through clojure data structures. Used by enlive, c2, and sablono.
* [Tower](https://github.com/ptaoussanis/tower) is a Clojure i18n & L10n library.
* [Elastisch](http://clojureelasticsearch.info/) elasti search library in Clojure.

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

### Development Environments

* [clojure-emacs shortcuts](https://github.com/clojure-emacs/cider#keyboard-shortcuts)

## ClojureScript

### Getting started
 * [Lighttable Clojurescript intro by David Nolen](https://github.com/swannodette/lt-cljs-tutorial)
 * [Modern CLJS](https://github.com/magomimmo/modern-cljs)
 * [Differences from Clojure--on the Clojurescript repo](https://github.com/clojure/clojurescript/wiki/Differences-from-Clojure)

### Resources
 * Clojurescript [Cheatsheet](http://appletree.or.kr/quick_reference_cards/Others/ClojureScript%20Cheat%20Sheet.pdf)
 * Sharing code between clojure and clojurescript: [cljx](https://github.com/lynaghk/cljx)
 * Compiling clojurescript in advanced mode. [Background Article](http://lukevanderhart.com/2011/09/30/using-javascript-and-clojurescript.html), [Externs](http://blog.8thlight.com/taryn-sauer/2014/07/31/clojurescript-faux-pas.html), [More on Externs](http://swannodette.github.io/2014/03/14/externs-got-you-down/)
 * [ClojureScript.net Translations from JavaScript](https://kanaka.github.io/clojurescript/web/synonym.html)
 * [Modern ClojureScript](https://github.com/magomimmo/modern-cljs)

### Libraries

 * [Om](https://github.com/swannodette/om)
   * [React Refracted](https://www.youtube.com/watch?v=5hGHdETNteE), [reddit notes](https://www.reddit.com/r/Clojurescript/comments/2vnsis/seeing_reactjs_from_clojurescript_perspective/)
 * [Sablono](https://github.com/r0man/sablono) - like Hiccup for Om

### Testing

* [cljs.test](https://github.com/clojure/clojurescript/wiki/Testing) a port of clojure.test, includes async testing
* [How to debug CLJS](https://github.com/shaunlebron/How-To-Debug-CLJS)
* [Source maps](https://github.com/clojure/clojurescript/wiki/Source-maps) for debugging ClojureScript in the browser
* [ClojureScrip REPL](https://chrome.google.com/webstore/detail/clojurescript-repl/lmjjlapjpjeodaadkljnmdfbjpfddchm?hl=en) for Chrome
