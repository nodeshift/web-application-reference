# Styles

**TODO**

* inline vs. separate files?
  * one-off styles?

## Recommended Components

N/A

## Guidance

During our discussions it became clear that there are multiple ways of styling and that there is a lot of choice, but there was one common idea that kept re-occuring.  If you are using a CSS framework, be sure to use what that framework is using.

### CSS Frameworks

CSS frameworks are a great choice for developing applicaitons.  Some advantages are:

* Great for out-of-the-box prototyping
* customizable
* consistent

[Tailwind CSS](https://tailwindcss.com/) is a modern choice that the team has used.  Other recommendations that the team made are [Carbon](https://carbondesignsystem.com/) and [Patternfly](https://www.patternfly.org/) which are both IBM and Red Hat projects respectivly.

It is also important that if you are using a front-end JavaScipt framework, the CSS framework should fit into it.

### Layout Methods

Since it is generally harder to design for a smaller screen, the team recommends a mobile first and responsive approach to an applications layout.  When defining css rules it is recommended to put the rules for mobile first followed by the rules for other layouts that your application might have.

The use of [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) allows you to apply CSS styles to your application using various characteristics, such as sceen resolution and orientation.  Media Queries will help with the responsive approach to writing applications as mentioned above.

Another way of making an application responsive is with either the Grid or Flex layouts.  The team is familiar with both Grid and Flex, while Grid is slightly prefered.  Depending on the situation, both can be used.

Whichever layout method is used, Grid or Flex, will go hand in hand with using Media Queries

Of course, if you are using a CSS framework it is important to use whichever layout method is built in there.

### Preprocessors

While preprocessors are still being used, built-in css properties and rules are now starting to deprecate the use of preprocessors.

However, the team does prefer the use of the [Sass](https://sass-lang.com/).

Many of the popular front-end CSS and javascript frameworks used to create application have these processors built in, so if you are using a framework, it is always recommended to use what that framework is using.


### General

#### Units of Measurement

The team thought that it was important to stick with one for a consistent UI and consistecy across the application.  Some helpful recommendations that came out of our discussion where:

* rem - preferred for accesibilty and for fonts
* borders - these could be in **px**
* div tags - should be more percentage based

As mentioned earlier, if you are using a CSS framework, it is important to use what that framework is using.

Make sure to use the `viewport` metatags width/height, which will be helpful for the gloabl container and absoulte positiong.  Here is an example `viewport` for a mobile application

```
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

#### Vendor prefixes

Browser vendors would add prefixes to non-standard/new css properties for developers to experiment with.  The team recommends the use of the [autoprefixer](https://www.npmjs.com/package/autoprefixer) library, which is an industry standard.  While this might important when supporting older code, it is recommended to look at if and why you might need a prefix when creating new applicaitons.


### Additional Resources

[Comparing Modern CSS Solutions](https://www.youtube.com/watch?v=CQuTF-bkOgc)

