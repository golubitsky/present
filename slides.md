---
title: Refactoring - Golubitsky
separator: <!--s-->
verticalSeparator: <!--v-->
theme: black
revealOptions:

    transition: 'fade'

---

<style>
.font-red {
  color: red; 
}

.font-green {
  color: green; 
}
</style>

# <span class="font-green">Refactoring</span>

Mikhail Golubitsky  
Atlantis Technology  
June 2020  

<!--s-->

## Refactoring Résumé

<!--v-->

### Energy Production API

Extracted 3 <span class="font-red">copied-and-pasted</span> and <span class="font-red">untested</span> instances of an energy production algorithm

<!-- .element: class="fragment" -->

Established <span class="font-green">integration test harness</span> to generate fleet-wide estimates on-demand

<!-- .element: class="fragment" -->

Resulting REST API service had <span class="font-green">800+ unit tests</span>

<!-- .element: class="fragment" -->

Empowered team to <span class="font-green">deliver algorithm updates quickly</span>

<!-- .element: class="fragment" -->
Note: Used by sales, designers, reporting across all of Tesla Energy; v1 != v2 != v3, target changed to v4 (3/4 of the way through)

<!--v-->

### Other efforts

<!-- .element: class="fragment" -->

A refactoring  <span class="font-red">failure</span>

<!-- .element: class="fragment" -->

No/few/expensive existing tests

<!-- .element: class="fragment" -->

Too ambitious

<!-- .element: class="fragment" -->

Not enough <span class="font-green">understanding</span>

<!-- .element: class="fragment" -->

...smaller, incremental refactors

<!-- .element: class="fragment" -->

Note: 3 points climbing rule

<!--s-->

![https://www.thoughtco.com/the-allegory-of-the-cave-120330](./assets/allegory_of_the_cave.png "Plato's Cave")

Notes: A program is a frozen representation of an idea, a snapshot of a structure that once existed in a programmer's imagination. --Tom Stuart, Understanding Computation; Is there an ideal representation (program) of an idea?

<!--s-->

Understanding is <span class="font-green">emergent</span>

<!--s-->

## Emergence

![https://study.com/academy/lesson/emergent-properties-definition-examples.html](./assets/emergentprps.png "Emergent Properties")

Note: The arising of novel and coherent structures, patterns and properties during the process of self-organization in complex systems --Jeffrey Goldstein

<!--s-->

``` text
                 +------> Programming --------+
                 |                            |
                 |                            v
Requirements --> Understanding    Understanding --> Software
                 ^                            |
                 |                            |
                 |                            |
                 +------- Refactoring <-------+
```

Understanding is an <span class="font-green">emergent opportunity to refactor</span>

<!--s-->

## What is refactoring?

> The process of restructuring existing computer code **without changing its external behavior**

--Wikipedia

<!--s-->

<span class="font-red">Not</span> refactoring:

<div class="fragment">New features</div>
<div class="fragment">Fixing bugs</div>
<div class="fragment">Optimization</div>

<!--s-->

## Why refactor?

<div class="fragment">We often need to change <i>soft</i>ware</div>
<div class="fragment">Requirements change (we're human)</div>
<div class="fragment font-green">Change should be inexpensive</div>

<!--v-->

> Programs that are hard to read are hard to modify.

--Kent Beck

<!--v-->

> Loss of the structure of code has a cumulative effect. The harder it is to see the design in the code, the harder it is to preserve it, and the more rapidly it decays.

--Martin Fowler, Refactoring

Notes: **Fowler:** The purpose of refactoring is to make the software easier to understand and modify.

<!--s-->

> Preserving existing behavior is one of the largest challenges in software development.

> Legacy code is simply code without tests.

--Michael Feathers, Working Effectively With Legacy Code

<!--v-->

> I often refactor just when I'm reading some code. That way as I gain understanding about the program, I embed that understanding into the code for later so I don't forget what I learned.

--Martin Fowler, Refactoring

<!--s-->

## Tests

* Feedback re: nothing is broken  
* Fast
* Independent (from one another)
* Repeatable (not flaky)
* Written <span class="font-green">first</span> ([Uncle Bob explains why](https://www.youtube.com/watch?v=GvAzrC6-spQ))

Note: The suite of code is there so we are not afraid of our code. --Uncle Bob

<!--s-->

> What if you were a doctor and had a patient who demanded that you stop all the silly hand-washing in preparation for surgery because it was taking too much time?

--Robert C. Martin, Clean Code

<!--s-->

### Some practical tips

<!--s-->

> Master programmers think of systems as stories to be told rather than programs to be written.

* Robert C. Martin, Clean Code

<!--s-->

## Functions

* Naming
* <span class="font-green">Pure</span> (avoid <span class="font-red">state</span>)  

<!--s-->

### How to name functions

<div class="fragment">Reveal intent</div>
<div class="fragment">Nouns are for pure functions</div>
<div class="fragment">Verbs are for functions with side-effects</div>
<div class="fragment">Avoid disinformation</div>
<div class="fragment">Avoid mental translation</div>
<div class="fragment">Consistency</div>

Notes: Consistency: within function, file, module, project, team, company -- in descending order of importance

<!--s-->

### How to write functions

<div class="fragment">Short</div>
<div class="fragment">One level of abstraction</div>
<div class="fragment">Low cognitive load</div>
<div class="fragment">Low <i>n</i> arguments</div>
<div class="fragment">No side effects!</div>
<div class="fragment">Okay fine, but certainly not in business logic</div>

Note: Uncle Bob: 1) Functions should do one thing. They should do it well. They should do it _only_. 2) Functions should either _do_ something or _answer_ something, but not both.

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

## Law of Demeter (for OOP)

``` ruby
announcement.event.gold.source.attribute['source_system_code']
```

<!--s-->

> The proper use of comments is to compensate for our failure to express ourself in code.

* Robert C. Martin, Clean Code

Note: redundant, out of sync, opportunity to refactor

<!--s-->

Thank you!

![https://www.osnews.com/story/19266/wtfsm/](./assets/wtf-per-minute.jpg "WTF/m")

<!--v-->

> As the code gets clearer, I find I can see things about the design that I could not see before. Had I not changed the code, I probably never would have see these things, because I'm just not clever enough to visualize all this in my head.

--Martin Fowler, Refactoring

<!--v-->

> Refactoring is not an activity you set aside time to do. Refactoring is something you do all the time in little bursts. You don't decide to refactor, you refactor because you want to do something else, and refactoring helps you do that other thing.

--Martin Fowler, Refactoring
