# Cross-Platform

Developers often want their applications to be “cross-platform” so that they
can run on any platform their end-users wish to use. Platforms may include
different flavors of desktops (Windows, MacOS, Linux) or flavors of
mobile devices (Android, iOS).

Web applications are, by definition, cross-platform as they will run
anywhere a browser runs. With the wide availability of browsers across
platforms today, that means pretty much anywhere.

However, standard web applications running in a browser are not as
integrated into a platform as a native application, may be limited with
respect to what services they can use from the platform, and need connectivity
to be able to run. Organizations may want to achieve better integration
with platforms and to have their applications run off-line.

[Progressive Web Applications](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/What_is_a_progressive_web_app)
(PWAs) can achieve these capabilities
and can be used as a middle ground between native applications and
Hybrid applications. They improve interaction with native platforms
while staying closer to a standard Web application. However, iOS
users may find it more difficult to install PWAs due to a more limited
browser support and features. Additionally, users must be taught how
to install a PWA.

If more integration is needed than a PWA can provide, a common option
is to use a hybrid application which embeds a web application built
with standard Web technologies into a native application and
provides a higher level of integration into the native platforms.

Key ways for integrating a web application into a native application
include WebViews, [Chrome Custom Tabs](https://developer.chrome.com/docs/android/custom-tabs/),
and [Trusted Web Activities](https://developer.chrome.com/docs/android/trusted-web-activity/)
although the latter two are for Android only.

There are also frameworks that enable cross-platform development of native applications using a single codebase.  These produce native applications that do not use WebViews.

Tools for building hybrid applications often either target desktop (Windows, MacOS and Linux) and/or Mobile (Android, iOS).

## Recommended Components

N/A

## Guidance

Some team
members have experience in creating cross-platform applications
in previous roles, but we currently don’t have any guidance to share based
on experience within the team based on projects within Red Hat and IBM.

This reflects that for the applications we develop, most often the team
has seen either the use of a pure Web application which is accessible
across platforms and/or the use of individual solutions for specific platforms.
