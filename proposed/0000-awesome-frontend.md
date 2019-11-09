# 0000 - Awesome frontend

## Status
[status]: #status

Decided as "consens of the makers".

## Summary
[summary]: #summary

The [frontend](https://github.com/kartevonmorgen/kartevonmorgen) of the _Karte von morgen_ (KVM)
shall be accessible from multiple clients (browser, mobile) and the code shall be maintainable.
Therefore some changes are needed in the existing technical practices.

## Context
[context]: #context

The current frontend code is in a bad state. It is imperative to address this situation immediately.
The following issues **need to be solved**:

- _Maintainability_  
  Due to the untyped programming language JavaScript most types of code refactoring are risky to realize.
  This gets emphasized by external dependencies that easily can break the web application.
  Often a simple dependency update leads to multiple hours of fighting the dependency hell.
  Unfortunately a handful of bugs don't occur during the refactoring process but during the
  runtime (because JS can't check correctness at compile time).

- _Complexity_  
  The current complexity of the codebase is grown due to a lot of dirty quick fixes.
  This not only makes it hard for the community to contribute to the project
  but it also makes it costly to introduce new features.
  
  Besides, the [usage of JSX](https://reactjs.org/docs/react-without-jsx.html) is
  neither intuitive nor [KISS](https://en.wikipedia.org/wiki/KISS_principle).
  Another templating engine is very much desirable.

- _Tests_  
  There are few tests but most of the code is untested.
  This makes it even harder to refactor and maintain the project.

- _File size_  
  The packed JavaScript bundle size was 5.3 MB some time ago.
  In the meanwhile its shrunken to 1.5 MB but that's still a bunch of bytes that
  needs to be downloaded at once, which is unbearable for some connection cases (old devices).

On the other hand, there are some **points to be taken into account**:
- _Current status_  
  - KVM is not far away from MVP.
    It would be sensible to reach that milestone before attempting the needed rewrite,
    which will be quite energy-consuming, especially at this point of time.

  - Most of the frontend implements presentation, not business logic,
    and should be easy to port at any time.
  
  - Many features or sections are unrelated to one another and 
    can fortunately be considered and written separately, at will.

- _Disponibility of Typescript_  
  As a typed language compatible with JS, its usage would certainly be a step forward, 
  even if not efficient enough to solve all current issues.

- _Runtime and Package management_  
  Node/npm is a combo that provokes dependency management hell.
  It would be nice to get rid of it, but it is needed 
  at least for [testing](https://medium.com/javascript-scene/tdd-changed-my-life-5af0ce099f80),
  and [deno](https://deno.land/std/manual.md#introduction) is far from production ready.
  
  We are open to new options in this regard.

- [_Svelte_](https://svelte.dev/)  
  As a lightweight, component-based, compiled framework with a pretty low learning curve,
  which needs less code and offers greater performance and long-term sustainability.
  it is a sound alternative to the current tools in KVM.

## Decision
[decision]: #decision

**We will port the frontend step by step to Svelte in Typescript with the appropriate tests**,
starting at the next big feature ([discuss ratings](kartevonmorgen/kartevonmorgen/issues/515), 
where [Miguel San Miguel](miguelsan) commits himself towards implement this).

The resulting compiled code (HTML/CSS/JS), will be integrated into the current frontend.
Once enough features have been moved to Svelte, the app in its current form can be discarded.

In the long run we also wish an [automatised CI-CD system](
https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment).

We made this decision based on following reasons.
We expect to achieve

- an MVP **project status** without critical intervention, whilst opening a sustainable path for the future
- respecting **modularity**, so that we can comfortably transit from one technology to the other
- a reduced **complexity** because we can refactor and get rid of most legacy code by following best TDD practices 
- a much better **maintainability** because:
  - TS is statically typed
  - refactoring is easy (compiler and tests do a very good job)
  - [alternative package managers](https://github.com/kartevonmorgen/kartevonmorgen/issues/614#issuecomment-550396931)
    can provide reliable dependency management
  - most mistakes will popup at compile-time
- a mobile friendly **file size** because the compiler drops all boilerplate code not in use
- [declarative, state- and event-driven UI development](
  https://svelte.dev/blog/virtual-dom-is-pure-overhead#Why_do_frameworks_use_the_virtual_DOM_then)
  and real **reactivity** [unlike React](
  https://svelte.dev/blog/svelte-3-rethinking-reactivity#Moving_reactivity_into_the_language)

## Consequences
[consequences]: #consequences

The decision has the following consequences:

- developers need to know or learn TS, but the importance of this is negligible for those already knowing JS
- mastering Svelte should be straightforward
- we might need to agree on a set of guidelines for TDD on the browser
  (tests first, test coverage, critical balance between Unit and Integration Testing, etc)
- [Leaflet](https://leafletjs.com/) can be still be integrated, as well as other JS libraries if needed
  (although we want to keep them at a minimum, specially on the side of the code been delivered)
- the admin frontend of the OpenFairDB can be written as a independent module or merged into the frontend
- we can't use component libraries that are based on React, but those based on Vue could be easily transported
- the app might [need polyfills](https://github.com/sveltejs/svelte/issues/558) to work with old browsers

## References
[references]: #references

- http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions
