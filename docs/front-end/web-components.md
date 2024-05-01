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

Broadly speaking, every web component is a custom element - a specific, globally-recognized tag-name which becomes associated with a class extending HTMLElement in JavaScript. Web components can also make use of the related technologies.
 
## Recommended Components
- [Lit](https://lit.dev) (for authoring components)
- [Web Dev Server](https://modern-web.dev) / Web Test Runner (for unit tests and local dev)
- [Custom Elements Manifest](https://github.com/webcomponents/custom-elements-manifest) (for ide support / docgen / codegen)
- [PatternFly Elements](https://patternflyelements.org) Design System
- [Carbon Web Components](https://web-components.carbondesignsystem.com/) Design System

## Guidance

### Advantages and Ideal Use Cases

- mix and matching components
- a la carte / low impact development
- cross-team collaboration
- design systems
- migrating piecemeal from older frameworks

### Potential Gotchas When Using Web Components

- cross-root aria
- double-registration errors
- server-side tooling / ssr limitations
- shadow dom can be a double edged sword

### Our Experiences Using Web Components at Red Hat

- Design Systems 
  - PFE
  - RHDS
- HTML-first / MPAs
- SPA usage (high javascript, state-management)

## Further Reading
