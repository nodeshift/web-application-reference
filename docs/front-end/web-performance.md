# Web Performance

In today’s fast paced digital age, first impressions are everything. The speed at which user experiences are perceived on a user’s end are very crucial for conversion rates and user retention. In our development experiences, we have observed web performance to be one of the most important aspects of building a successful site or a web application. If a webapp or a site has poor performance, it tends to provide a negative user experience thereby impacting in lost business, customers or users. On the other hand, a higher-performance and more responsive app leads to a better user experience which is key in gaining and keeping users. Our prior digital experiences have confirmed that web application performance can directly influence revenue, time spent on the site, page views, search traffic, and user retention.

Developers at IBM and Red Hat have incorporated a Web Performance Culture that is focussed on prioritizing speed, visual stability and efficiency. A combination of these factors helps alleviating bounce rates, improving conversions, and in turn enhancing user satisfaction. From our own experiences, involves collaborative development at the intersection of content management, frontend, backend and the network layer. Based on the research done at IBM and Red Hat and reviewing the discussions of the W3C Web Performance Working Group, we’ve summarized the important metrics to measure below.

Although "slow" and "fast" are very subjective per user, studies in human-computer interactions and feedback from UXR studies done in IBM & Red Hat have provided us with some general rule of thumb numbers:

- Up to 250ms, everything feels instant.
- Up to 750ms, UI feels rapid, with short loading animation which becomes noticeable.
- Up to 1500ms, loading animation is heavily dominant in the page perception, but page still feels usable.
- Above 3 seconds, 70% of the people will start avoiding the UI if they can.
- Over 5 seconds, your application is considered 'broken' or unusable.

## Important metrics to measure

As a performance minded team, our teams regularly incorporate performance assessment in order to measure how a site or a web app is performing from an user’s perspective.

**First paint (FP)**: This metric measures the time when the navigation happens from the browser to the first pixels on the screen. It is usually when the page first starts rendering, an example could be an empty box with no content or something as subtle and uninformative as a change in the background color.

**First Contentful Paint (FCP)**:  This metric is the measurement of time when a page starts loading (DOM getting loading on the page) to when any part of the page's partial content gets rendered on the screen. Usually SVGs, images, canvas render, text etc. As an user it can be thought as the total time taken from the beginning of your page load to the time any content gets rendered on the screen.

**First Meaningful paint (FMP)**: This metric is the measure of amount of time it takes for the first useful or meaningful (for the user) element to be displayed on the screen. Usually the time at which an user can notice and perceive the primary content of the visible page.

**Largest Contentful Paint (LCP)**: This metric is the measure of time it takes for a site/ app to render the element containing largest amount of content. It is part of the three Core Web Vitals that Google uses to measure a page’s user experience. The other two being:
    **First Input Delay (FID)**: The measurement of time it takes for the visitor to perform their first action (example: clicking a link, pr button) and when the site responds.
    **Cumulative Layout Shift (CLS)**: This metric pertains to the extent to which a page’s layout shifts while it loads. This is important because you wouldn’t want page elements to shift while an user is interacting with the user interface.

**Interaction to Next Paint (INP)**: This metric measures or observes the latency of every tap, click, or keyboard interaction that happens on the page. The amount of elapsed time between a user interaction like a click or key press and the next time the user sees a visual update on the page is factored into the calculation.

**Total Blocking Time (TBT)**: This metric measures the total amount of time your site was blocked thereby preventing the user from interacting with the sections of your site or page.

**Cumulative Layout Shift (CLS)**: This metric focuses on measuring visual stability. It is the cumulative score of all unexpected layout shifts that occur when the page starts loading and when its lifecycle state changes.

**Time to First Byte (TTFB)**: This metric measures the time it takes for the network to respond to a user request with the first byte of a resource. Its the time taken between the request for a resource and when the first byte of a response arrives client side.

## Factors Affecting Web Performance

Sites that perform poorly end up driving users away whereas sites that load quickly receive more traffic and result in better conversion rates. Our development teams have quantified the factors into three high level categories: Code, Network conditions, and Hosting/ location. Following are some key factors that affect web performance.

**Code**:
    **Page Weight**: Render blocking, broken and uncompressed JavaScript and CSS files cause significant dips in performance. If the page is not optimized, and we have heavy JS scripts loading right at the start it will take longer for the browser to download it on client side.
    **File Types & Images size**: A general rule of thumb is that the larger your file sizes are and the more files you have to load on a page/ website, the longer it will take to load in the browser. Minification of code and optimizing image formats and sizes have worked well in our experience to alleviate these issues. It is also important to serve scaled-down images for mobile devices to reduce data consumption in turn improving load times. The size, number and file type play a vital role in website performance in general.
    **Excessive redirects**: A plethora of redirects could be detrimental to a site's performance adding latency to the overall page load time. The impact will be seen clearly in the Time to First Byte (TTFB).

**Not leveraging browser caching**:
    **Network conditions / Latency**: The amount of time it takes to transfer information over the network from the client to the server can directly impact performance. CDN or network issues between source and end user end up slowing down the site speed. Furthermore, bottle necked outbound connections from the site itself and if the site is fetching data from multiple sources result in performance degradation. Bandwidth limitations could directly affect the speed as well.
    **Server/ Hosting**:Server capacity bottlenecks like concurrent connections or certain threads limitations or other tiers bottlenecks can also have a major impact on the speed of the site.
    If the web host doesn’t offer good performance at the server level, it would directly result in slower server response times.

## Techniques for Improving Web Performance

During our experiences, we have incorporated some techniques to improve web performance in our applications. This can serve as a checklist before releasing or deploying code out to production environments

- Optimize server performance and response times
  - Reducing processing time on the server
  - Optimizing database level queries, rewriting slow queries
  - Implementing server-level caching mechanism

- Using a content delivery network (CDN)

- Optimize Download Size Assets
  - Optimize web fonts
  - Optimize images plus lazy load images and video
  - Optimize CSS and JavaScript. Eliminate render-blocking scripts, and defer these scripts until other elements finish loading
  - Utilize image, video and text compression

- Optimize resource priorities
  - Avoid unintentional loading of resources

- Implement Caching
  - Cache images, CSS files, or JavaScript files
  - Enable cache control headers on your web server

## Setting performance budgets

During our experiences, our teams have learnt that investing time in using performance budgets goes a long way in preventing regressions. Web performance budget refers to a threshold or measurable limits or goals that teams outline for the metrics that matter the most. Once set, monitoring tools can be configured accordingly to send alerts passively, or break the build actively once the allocated budgets are violated. These set of limits imposed on metrics are very crucial in achieving business goals effectively. Adoption of a disciplined approach like this in our organizations has benefitted software teams immensely.

The key metric KPIs used for web performance budgeting can be classified into the following categories:

- Rule based metrics
- Time based metrics
- Quantity based metrics
- Custom metrics

Development teams at IBM and RedHat have recommended the starting with a Minimum Viable Performance Budget. Some examples of metrics could be the following:

- Total page size
- Total number of HTTP requests
- Page load time on mobile networks
- First Contentful Paint (FCP)
- Long Contentful Paint (LCP)
- Total Blocking Time (TBT)
- Total JavaScript Size in Bytes

As you try to refine your target budgets, performancebudget.io is a great resource offering visual aid presets for different network speeds.

## Tools

Integrating tools in day to day development workflows will simplify the way developers approach web performance. Wiring a tool with the performance budgets or even alerting in your CI/CD process can assist as a guide to measure speed, prioritize various features and optimizations.

[Webpack performance features](https://webpack.js.org/configuration/performance/)
[bundlesize](https://github.com/siddharthkp/bundlesize)
[Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci)

With a plethora of tools available, it’s difficult to choose the right solution for your development teams. Through our developer experiences, we’ve noted that every tool shows different results based on the desired objective. Our recommended approach is to use a variety of tools to get a comprehensive overview of your site or application performance. Validating performance on different devices, locations, and browsers will be a good first step in forming a baseline for important KPIs to measure.

At the bare minimum every developer should use the dev tools to find the biggest blockers & heavy files. Chrome Dev Tools > Network Tab. There is also a Lighthouse Tab that can be used to run in Chrome dev tools. Make sure to use it in incognito with no extensions installed.

Various teams at IBM and RedHat have identified the following tools that can be leveraged in the development workflows. [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview), [PageSpeed Insights](https://pagespeed.web.dev/), [WebPageTest](https://www.webpagetest.org/), [CrUX](https://developer.chrome.com/docs/crux), [Sitespeed.io](https://www.sitespeed.io/), [SpeedCurve](https://www.speedcurve.com/), [Calibre](https://calibreapp.com/), [new relic](https://newrelic.com/), [boomerang](https://github.com/akamai/boomerang), [batchspeed](https://batchspeed.com.atlaq.com/), [GTmetrix](https://gtmetrix.com/), [pingdom](https://www.pingdom.com/), [SpeedMonitor.io](https://speedmonitor.io/) are some of the widely used tools in the web engineering spectrum.
