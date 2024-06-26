# Web Accessibility

Accessibility is a mode of developing your website or application that anyone regardless of their physical, cognitive, or current ability can navigate, interact, and contribute to that website. The focus lies on making your user experience usable by as many people as possible. The official reference would be [WCAG](https://www.w3.org/WAI/WCAG22/quickref/). It's a list of things a developer is supposed to do to make a site more accessible for people with disabilities. This doesn't just cover people who are blind. It also includes people with color vision problems, partial deafness, physical impairment, advancing age, etc.

The [Web Content Accessibility Guidelines](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG) has summarized down the core concepts into 4 principles, referred to as POUR:

- Perceivable: Any user should be able to perceive it in some way, using one or more of their senses.
- Operable: Any user must be able to use controls, buttons, navigation, and other interactive elements by themselves (e.g. buttons must be clickable using mouse, keyboard, voice command, etc.). Additionally, it takes into account that disabled users will use assistive technology like voice recognition, keyboards, screen readers, and so on.
- Understandable: Any user should be able to understand the content.
- Robust: The content should adhere well-adopted web standards that are functional cross-browsers, now and in the future.

## Guidance

Staying updated on the latest trends, tools, and advancements in accessibility is crucial for ensuring that our team remains well-informed and knowledgeable about evolving standards. Through our experience, we did realize that a lot of the obvious things can be automated, however a majority of accessibility issues that impact users are things that are difficult or impossible to programmatically determine. As developers, we are aware about the importance of making our websites/ apps accessible to all users, but the journey to achieving this can be quite complex. Interacting with end users, our team understood that accessibility is necessary towards establishing your brand as inclusive and socially responsible, which is fairly important in today's markets.

Before we understood on how to implement web accessibility, the teams at IBM & Red Hat first started with who is behind this initiative. There’s quite a few acronyms for the organizations, projects, and guidelines themselves, so let’s break those down first.

Before our developers started to implement web accessibility, they looked into the communities that are behind this initiative. Diving through the resources, we observed there are a plethora of acronyms for various organizations, projects, and guidelines - so there’s a short summary on who sets the guidelines for web accessibility

- W3C: The World Wide Web consortium (W3C), the organization that sets standards for web accessibility compliance.

- WAI: Web Accessibility Initiative (WAI) is W3C’s initiative for creating the guidelines.

- WCAG: The actual accessibility guidelines are the Web Content Accessibility Guidelines (WCAG).

There are three levels of web accessibility that teams can aim to achieve. Following levels exist as a part of the guidelines and each level covers guidelines from previous levels before advancing to the next level.

- A Level: The easiest level of difficulty to implement with least guidelines to follow. It is the baseline for all websites to adhere by.  
- AA Level: This live includes A-level guidelines, and several other detailed design-specific guidelines. It is mid-level of difficulty to implement.
- AAA Level: This level includes all previous levels’ guidelines in addition to advanced details with respect tp animations and content.

In our product development experiences at IBM, we’ve found that to be fully compliant teams will need to meet all three standards: WCAG 2.1, US Section 508, and EU’s EN 301 549 standards. Links to [IBM accessibility requirements](https://www.ibm.com/able/requirements/requirements/), [Red Hat  accessibility requirements](https://www.redhat.com/en/about/digital-accessibility)

Here are reference resources provided in the WCAG docs which should be your first point of reference.

- How to Meet [WCAG](https://www.w3.org/WAI/WCAG22/quickref/?versions=2.1) (Quick Reference)
- Index of [ARIA Design Pattern](https://www.w3.org/WAI/ARIA/apg/) Examples

Other links:

- [W3C WAI Tutorials](https://www.w3.org/WAI/tutorials/)
- [MDN Accessibility guide](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML])
- [WebAIM Articles](https://webaim.org/articles/)
- [A11yProject](https://www.a11yproject.com/)
- [HTML5 Accessibility](https://www.html5accessibility.com/index.html)
- [Inclusive Components](https://inclusive-components.design/)

## Tools

In addition to keeping up to date with constantly evolving WCAG guidelines, instances or considerations around ensuring proper color contrasts to implement keyboard navigation and screen reader compatibility can be an extensive list. From our past experiences, we've realized that this is where tools can be a win to simplify the entire process. These tools assist in automating a lot of the heavy lifting, like scanning for common accessibility issues and suggesting possible fixes. It's a good balance between saving time, addressing accessibility related issues as well educating about best practices in accessibility. Some of the tools widely used in the community:

- [IBM Accessibility Checker](https://www.ibm.com/able/toolkit/tools/)
This is the tool offered by IBM. You can find a web version (chrome and firefox extensions) and the [npm](https://www.npmjs.com/package/accessibility-checker) library on the site. The tool uses IBM's accessibility rules engine detecting WCAG 2.1 accessibility issues for web-based content or applications. Checkout [IBM Accessibility Central](https://pages.github.ibm.com/IBMa/able/) to better understand accessibility and making software accessible at IBM.
IBM's Developer [guidelines and checklist](https://www.ibm.com/able/guidelines/index.html).
- [Tools List by W3C](https://www.w3.org/WAI/test-evaluate/tools/list/)
- [Pa11y](https://pa11y.org/)
- [Axe](https://github.com/dequelabs/axe-core)
- Using Lighthouse with hints in Chrome inspector

Other than the automated tools, manual testing methods are also used for accessibility testing. Following methods are used after a first pass with automated tools is completed.

- Content Review
Navigating and reading through content with accessibility best practices in mind.
- Keyboard Testing
Checking if all interactive elements can be operated with a keyboard.
- Screen Reader Review
Using a screen reader to test and uncover issues with reading order and interactive elements.

Recommendations of manual accessibility testing tools:

In our experiences, our team has found the following tools to be a good fit in their development workflows:

- [Wave](https://wave.webaim.org/)
- [BrowserStack](https://www.browserstack.com/accessibility-testing)
- [HeadingsMap](https://chromewebstore.google.com/detail/headingsmap/flbjommegcjonpdmenkdiocclhjacmbi) extension.

This It allows users to quickly see an outline of the page's heading levels and HTML5 tags. If someone skipped a heading level (eg: went from h2 to h4), this tool helps identify it.

## High Level checklist on ways to make your site/ application more accessible

Through our development workflows, creating an accessibility checklist for the team to always refer is a good way to help the entire team to learn about accessibility.

### Images and alt attributes

Use the alt attribute when using images. Add a descriptive alternative text for the image. Additionally, have alt texts so that users who have network issues will have an idea of the image before they see it.

### Links and context

Accessible hypertext links are very important aspects for accessible web pages and documents.
Accessible links are not just helpful for people with disabilities, well-written link text descriptions enhances user experience for any user. Following are some high level guidelines that should be followed:

1. Ensure concise, descriptive and meaningful anchor text. Also avoid using "click here", "read more" or "learn more" as link text.
2. Avoid capitalization all letters in links
3. Avoid usage of URLs for link text, and limit use of redirects
4. Avoid using the word "link" as part of the link text
5. Avoid using tooltips/screentips to add additional information

### Add Keyboard navigation

Create an accessible experience for keyboard users by making sure disabled users can access all interactive elements of your site/ app. Avoid attaching event listeners to non-interactive elements like `<div>` whenever possible. Use interactive elements like `<button>` and `<a>` instead.

### ARIA Landmarks and HTML Semantics

ARIA landmarks are attributes that should be added to an element to define roles on the site. HTML semantic elements and ARIA landmarks help screen readers know where they are going, and assist to easily jump from one section to another. Landmarks can be added using the role attribute. Add ARIA attributes sparingly, and only when HTML does not already express the intended semantic. Example: no need to add `aria-disabled="true"` if the element already has a HTML5 disabled attribute.

As a user there are a bunch of different ways to mark up your content. To structure your content, there are [100+ semantically meaningful elements](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantic_elements) available in addition to the ability to create custom elements.

### Make Video and Multimedia Accessible

A combination of things like choosing an accessible media player, adding captions, and using the right colors and font. Note to avoid accessibility barriers when planning, scripting, storyboarding, and recording your media.

### Keep Contrast Sensitivity in Mind

The color choices and the relationships between those hues can impact user experience drastically. If colors with not enough contrast are chosen, portions of the site/ app may appear hard to read and navigate for people with visual impairments. A rule of thumb would be to avoid color combinations that could be hard to distinguish from one another. The luminosity contrast ratio could be used to design with low contrast sensitivity in mind.

### Control focus with tabindex, stylefocus

Keyboard-only users should be able to perceive where focus is at all times and visible elements with focus should be viewable.

### Make transitions and animations accessible

Users should be able to pause, stop, or hide moving content. Additionally, there should be options available for users to turn off motion animation
