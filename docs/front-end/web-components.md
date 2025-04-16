# Web Components

The [WHATWG](https://html.spec.whatwg.org/multipage/custom-elements.html) and [WICG](https://github.com/WICG/webcomponents) maintain suite of web technologies and specifications including (but not limited to)

- [Custom Elements](https://html.spec.whatwg.org/multipage/custom-elements.html#custom-elements)
- [Shadow DOM](https://dom.spec.whatwg.org/#shadow-trees)
- The [`<template>` element](https://html.spec.whatwg.org/multipage/scripting.html#the-template-element)
- The [`<slot>` element](https://html.spec.whatwg.org/multipage/scripting.html#the-slot-element)
- [`ElementInternals`](https://html.spec.whatwg.org/multipage/custom-elements.html#element-internals)
- [CSS Custom Properties](https://drafts.csswg.org/css-variables/)
- [Module scripts](https://html.spec.whatwg.org/#module-script)

These are collectively referred to as "web components", and represent the browsers' native component model for web developers.

Broadly speaking, every web component is a custom element - a specific tag-name which becomes associated with a class extending HTMLElement in JavaScript. Web components can also make use of the related technologies.

## Recommended Components

- [Lit](https://lit.dev) (library and framework for authoring components)
- [Web Dev Server](https://modern-web.dev) / Web Test Runner (for unit tests and local dev)
- [Custom Elements Manifest](https://github.com/webcomponents/custom-elements-manifest) (for ide support / docgen / codegen)
- [PatternFly Elements](https://patternflyelements.org) Design System
- [Carbon Web Components](https://web-components.carbondesignsystem.com/) Design System
- [Web Components Community Group](https://github.com/w3c/webcomponents-cg/)

## Guidance

### Our Experiences Using Web Components at Red Hat

The team at Red Hat has been involved in several Web Component projects and have learned a good amount about Web Components and how to write them

Two Web Component "Systems" at Red Hat are

- [PatternFly Elements](https://patternflyelements.org/) (aka PFE)  (“upstream”)
- [Red Hat Design System](https://ux.redhat.com/) (aka RHDS) (“downstream”)

### Advantages and Ideal Use Cases

Through the teams experience with Web Components, we've identified a few different pros and cons when using Web Components and what type of applications you might want to use them with.

#### Accessibility

a single implementation of complex ui patterns can help teams to ship accessible experiences with less fuss

#### Work Across frameworks / Cross Team Collaboration

the same `<rh-card>` which works in drupal can work the same way in react, or in an ejs template, and the teams working with those components can transfer that knowledge to other projects, instead of reimplementing design specs for each new framework.

#### Design Systems

The case for web component-based design systems is strong because of encapsulation / knowledge transfer / future proofing as described above. These can also include a certain amount of business logic like analytics code, personalization, etc (ymmv)

#### Microfrontends

This is another case where web components and shadow dom shine, as the encapsulation guarantees and framework interoperability aspects lend themselves naturally to enabling teams to cooperate while maintaining boundaries.

#### Greenfield SPA

There’s an argument to be made from a loading / rendering perf and future-proofing perspective to start new projects with a web component framework (like lit, stencil, hybrids, FAST, etc) in place of traditional / legacy framework (angular, react, vue)

docs.redhat.com (a greenfield project) leaned heavily on RHDS web components, and that helped ship the project faster

#### Piecemeal migration

The framework interoperability aspect enables upgrading complex projects on a component-by-component basis. Rather than break the entire app when bumping the underlying frontend-framework from vX to vY, replace components one by one with interoperable web components.

### Common Gripes

As with all programming models, there are some gotchas that the team has encountered:

- cross-root aria
  - To prevent a11y failures, signifacant expertise might be needed

- double-registration errors when bundling modules. we recommend using a global import map for each page
- Server-side Rendering (SSR) gotchas. When using the `lit-ssr` library to generate [declarative shadow DOM templates](https://web.dev/articles/declarative-shadow-dom), hydration mismatches when client initial state differs from server rendered state can be difficult to recover from.
- shadow DOM can be a double edged sword. Teams which are unused to it may find it difficult to work with at first

- Unit Testing
  - JSDOM/Jest may not work with your custom elements: teams may have to author their components with node environments / DOM shims in mind, which can increase payloads to the client in some cases.
  - [@open-wc/testing](https://open-wc.org/docs/testing/testing-package/) is a testing framework that the team has had success with.

### General Concensus

Authoring web components: If you have a team with web platform experience, that always have an MDN tab open, and you’re hopeful to leverage current and future web standards like PWA, then you’re likely to succeed. If on the other hand you don’t have much senior experience or depth of knowledge on web platform features, you may run into issues. However, your teams that overcome those issues will gain platform knowledge and not just framework knowledge.

Using web components inside of other major frameworks: our teams have consistently reported that consuming web components inside other frameworks is typically a turnkey developer experience which saves time and reduces duplication of effort.

Since Web Components rely on code that is already in the browser, they reduce the page load for the end user.

#### Resources

- [Vaadin lit vs Reac Performance Comparision](https://www.youtube.com/watch?v=CJYkwDTaHzY)
- [Page Loading Comparison - 2023 Devconf.cz](https://bennypowers.dev/decks/devconf-brno-2023/#slide-27/step-1)
