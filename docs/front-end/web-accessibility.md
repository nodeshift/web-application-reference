# Web Accessibility

Accessibility is a mode of developing your website or application that anyone regardless of their physical, cognitive, or current ability can navigate, interact, and contribute to that website. The focus lies on making your user experience usable by as many people as possible. The official reference would be (WCAG)[https://www.w3.org/WAI/WCAG22/quickref/]. It's a list of things a developer is supposed to do to make a site more accessible for people with disabilities. This doesn't just cover people who are blind. It also includes people with color vision problems, partial deafness, physical impairment, advancing age, etc.

The [Web Content Accessibility Guidelines](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG) has summarized down the core concepts into 4 principles:

- Perceivable: Any user should be able to perceive it in some way, using one or more of their senses.

- Operable: Any user must be able to use controls, buttons, navigation, and other interactive elements by themselves (e.g. buttons must be clickable using mouse, keyboard, voice command, etc.). Additionally, it takes into account that disabled users will use assistive technology like voice recognition, keyboards, screen readers, and so on.

- Understandable: Any user should be able to understand the content.

- Robust: The content should adhere well-adopted web standards that are functional cross-browsers, now and in the future.


## Guidance 

A lot of the obvious things can be automated, however a majority of accessibility issues that impact users are things that are difficult or impossible to programmatically determine. As developers, we are aware about the importance of making our websites/ apps accessible to all users, but the journey to achieving this can be quite complex. Here are reference resources provided in the WCAG docs which should be your first point of reference.

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

In addition to keeping up to date with constantly evolving WCAG guidelines, instances or considerations around ensuring proper color contrasts to implement keyboard navigation and screen reader compatibility can be an extensive list. This is where tools can be a win to simplify the entire process. These tools assist in automating a lot of the heavy lifting, like scanning for common accessibility issues and suggesting possible fixes. It's a good balance between saving time, addressing accessibility related issues as well educating about best practices in accessibility. Some of the tools widely used in the community:

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

- [Wave](https://wave.webaim.org/)
- [BrowserStack](https://www.browserstack.com/accessibility-testing)

## Ways to make your site/ application more accessible 

- Images and alt attributes

Use the alt attribute when using images. Add a descriptive alternative text for the image. Additionally, have alt texts so that users who have network issues will have an idea of the image before they see it.


- Links and context
- Add Keyboard navigation 
- ARIA Landmarks and HTML Semantics

ARIA landmarks are attributes that should be added to an element to define roles on the site. HTML semantic elements and ARIA landmarks help screen readers know where they are going, and assist to easily jump from one section to another. Landmarks can be added using the role attribute. Add ARIA attributes sparingly, and only when HTML does not already express the intended semantic. Example: no need to add `aria-disabled="true"` if the element already has a HTML5 disabled attribute.

- Make Video and Multimedia Accessible
- Keep Contrast Sensitivity in Mind
- Control focus with tabindex, stylefocus
- Make transitions and animations accessible
