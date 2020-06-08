---
title: Refactoring - Golubitsky
separator: <!--s-->
verticalSeparator: <!--v-->
theme: white
revealOptions:

    transition: 'fade'

---

# Refactoring

Mikhail Golubitsky  
Atlantis Technology  
June 2020  

<!--s-->

## My Biggest Refactoring* Project

* From 3 different applications extract a copied-and-pasted energy production algorithm.

* Resulting REST API service had 800+ unit tests.

<!-- .element: class="fragment" -->

* Smaller, incremental refactors throughout my programming career.

<!-- .element: class="fragment" -->

Note: v1 != v2 != v3, target changed to v4 (3/4 of the way through)<br>
<!--s-->

> A program is a frozen representation of an idea, a snapshot of a structure that once existed in a programmer's imagination.

--Tom Stuart, Understanding Computation
<!--s-->

<!-- .element: class="fragment" -->
Understand intent.
<!-- .element: class="fragment" -->
Understanding can be an emerging property of our work.
<!-- .element: class="fragment" -->
Understanding is an opportunity to refactor.
<!-- .element: class="fragment" -->

<!--s-->

## What is refactoring?

<!-- .element: class="fragment" -->

> The purpose of refactoring is to make the software easier to understand and modify.

<!-- .element: class="fragment" -->

> Refactoring does not change the observable behavior of the software.

<!-- .element: class="fragment" -->

## Why refactor

> Programs that are hard to read are hard to modify.

--Kent Beck

> Loss of the structure of code has a cumulative effect. The harder it is to see the design in the code, the harder it is to preserver it, and the more rapidly it decays.

<!-- .element: class="fragment" -->
--Martin Fowler, Refactoring
<!--s-->

> I often refactor just when I'm reading some code. That way as I gain understanding about the program, I embed that understanding into the code for later so I don't forget what I learned.

--Martin Fowler, Refactoring

<!--s-->

> As the code gets clearer, I find I can see things about the design that I could not see before. Had I not changed the code, I probably never would have see these things, because I'm just not clever enough to visualize all this in my head.

--Martin Fowler, Refactoring

<!--s-->

## Always Be Refactoring

> Refactoring is not an activity you set aside time to do. Refactoring is something you do all the time in little bursts. You don't decide to refactor, you refactor because you want to do something else, and refactoring helps you do that other thing.

--Martin Fowler, Refactoring

<!--s-->

* Problem domain.
* Solution domain.

<!--s-->

<!-- .element: class="fragment" -->

> Functions should do one thing. They should do it well. They should do it only.

<!-- .element: class="fragment" -->

> Functions should either do something or answer something, but not both.

<!-- .element: class="fragment" -->

* Robert C. Martin, Clean Code

<!--s-->

> Master programmers think of systems as stories to be told rather than programs to be written.

* Robert C. Martin, Clean Code

<!--s-->

* Short.
* One level of abstraction.
* _n_ arguments <= 3 is best.
* No side effects.
  + Certainly not in business logic.

<!--s-->

> What if you were a doctor and had a patient who demanded that you stop all the silly hand-washing in preparation for surgery because it was taking too much time?

--Robert C. Martin, Clean Code

<!--s-->

> The proper use of comments is to compensate for our failure to express ourself in code.

* Robert C. Martin, Clean Code

Note: redundant, out of sync, opportunity to refactor

<!--s-->

> ... you find it hard to make changes your users want. This is where refactoring comes in.

--Martin Fowler, Refactoring

<!--s-->

## Single responsibility principle

> A class or module should have one, and only one, reason to change.

--Robert C. Martin, Clean Code

<!--s-->

* Run the tests.
* No duplication.
* Expresses intent.
* Minimizes amount of code.

<!--s-->

* Law of Demeter (for OOP)

``` ruby
announcement.event.gold.source.attribute['source_system_code']
```

* Opportunity for refactoring.

<!--s-->

Legacy Code - testing.

--Michael Feathers, Working Effectively With Legacy Code

<!--s-->

* Fast
* Independent
* Repeatable

* [Uncle Bob explains why test "first"](https://www.youtube.com/watch?v=GvAzrC6-spQ)

<!--s-->

* Remove state.
* Naming.
  + Reveal intention.
  + Nouns (pure) and verbs (side-effects).
  + Avoid disinformation.
  + Avoid mental translation.
  + Avoid single-letter variables.
  + Consistency.

<!--s-->

![https://www.osnews.com/story/19266/wtfsm/](./assets/wtf-per-minute.jpg "WTF/m")

<!--s-->
