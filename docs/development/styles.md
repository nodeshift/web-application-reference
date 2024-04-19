# Styles

## Recommended Components

N/A

## Guidance

During our discussions it became clear that there are multiple ways of styling and that there is a lot of choice, but there was one common idea that kept recurring.  If you are using a CSS framework, be sure to use what that framework is using.

### CSS Frameworks

CSS frameworks are a great choice for developing applications.  Some advantages are:

* Great for out-of-the-box prototyping
* customizable
* consistent

[Tailwind CSS](https://tailwindcss.com/) is a modern choice that the team has used.  Other recommendations that the team made are [Carbon](https://carbondesignsystem.com/) and [Patternfly](https://www.patternfly.org/) which are both IBM and Red Hat projects respectively.

It is also important that if you are using a front-end JavaScipt framework, the CSS framework should fit into it.

### Layout Methods

Since it is generally harder to design for a smaller screen, the team recommends a mobile first and responsive approach to an applications layout.  When defining css rules it is recommended to put the rules for mobile first followed by the rules for other layouts that your application might have.

The use of [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) allows you to apply CSS styles to your application using various characteristics, such as screen resolution and orientation.  Media Queries will help with the responsive approach to writing applications as mentioned above.

Another way of making an application responsive is with either the Grid or Flex layouts.  The team is familiar with both Grid and Flex, while Grid is slightly prefered.  Depending on the situation, both can be used.

Whichever layout method is used, Grid or Flex, will go hand in hand with using Media Queries

Of course, if you are using a CSS framework it is important to use whichever layout method is built in there.

### Preprocessors

While preprocessors are still being used, built-in css properties and rules are now starting to deprecate the use of preprocessors.  It is also important to decide if the scope and scale of your project needs one.

However, the team does prefer the use of the [Sass](https://sass-lang.com/).

The team also agreed that it was important to be more CSS centric(native CSS features) even when using a preprocessor.  This was because the language is introducing more and more features, which will start to make these preprocessors deprecated.

Many of the popular front-end CSS and JavaScript frameworks used to create application have these processors built in, so if you are using a framework, it is always recommended to use what that framework is using.

### Linting

Similar to how developers [lint their JavaScript code](https://github.com/nodeshift/nodejs-reference-architecture/blob/main/docs/development/code-consistency.md) for code consistency, it is equally important to lint our CSS code.  A module that the team has had success with is [stylint](https://www.npmjs.com/package/stylint).

While the team doesn't make a recommendation on the linting rules, they do agree that a linter should be used and should be applied organization wide when applicable.


### General

#### Units of Measurement

The team thought that it was important to stick with one for a consistent UI and consistency across the application.  Some helpful recommendations that came out of our discussion where:

* rem - preferred for accessibility and for fonts
* borders - these could be in **px** - decorative / doesn't scale well
  * Borders are mostly decorative anyway, and using doesn't scale well when using something that are not pixels

As mentioned earlier, if you are using a CSS framework, it is important to use what that framework is using.

Make sure to use the `viewport` metatags width/height, which will be helpful for the global container and absolute positioning.  Here is an example `viewport` for a mobile application

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

#### Vendor prefixes

Browser vendors would add prefixes to non-standard/new css properties for developers to experiment with.  The team recommends the use of the [autoprefixer](https://www.npmjs.com/package/autoprefixer) library, which is an industry standard.  While this might be important when supporting older code, it is recommended to look at if and why you might need a prefix when creating new applications.

Autoprefixer is a plugin for [PostCSS](https://github.com/postcss/postcss), a tool for transforing styles.  PostCSS is used by industry leaders and the Autoprefixer plugin is on of the most popular CSS tools.

#### CSS Methodologies

CSS methodologies are formal, documented systems for authoring CSS.  The aim of a CSS methodology is to reduce the CSS footprint and help maintain large CSS codebases among developers.

* [Block, Element, Modifier(BEM)](https://getbem.com/) - component-based approach to web development. The idea behind it is to divide the user interface into independent blocks. This makes interface development easy and fast even with a complex UI, and it allows reuse of existing code without copying and pasting.

* CSS-in-JS is another pattern which uses JavaScript to style components. [styled-components](https://github.com/styled-components/styled-components) and [Emotion](https://github.com/emotion-js/emotion) are some of the popular CSS-in-JS libraries in the React community.

Most of the CSS frameworks employ some sort of CSS methodology and if you are using one it is important to follow whatever methodology that framework uses.

### Additional Resources

[Comparing Modern CSS Solutions](https://www.youtube.com/watch?v=CQuTF-bkOgc)
[CSS Methodologies](https://github.com/awesome-css-group/awesome-css#naming-conventions--methodologies-bulb)
[State Of CSS 2020 - Methodologies](https://2020.stateofcss.com/en-US/technologies/methodologies/)
