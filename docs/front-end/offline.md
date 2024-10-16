# Offline

Offline could mean multiple things in the context of Web Applications and it is important to be prepared for those different scenarios.

* No Network Connectivity - Truly Offline
* Limited/Spotty Network Connectivity - Also Known as Lie-Fi

Having no network connectivity is usually what is associated with the term offline, but having limited connectivity(Lie-Fi) is just as important to plan for.

## Offline options for Web Apps

For Web Apps, there is really only one option when planning for an Offline Application and that is Service Workers.

### Service Workers

Service workers essentially act as a proxy that sits between a web application, the browser, and the network. They allow a developer to intercept network requests, which can allow then to check the networks availability and load the application accordingly.

This will allow a web application developer to store the html, css, and js files into a cache in the browser, which can then be loaded from the Service Worker.

Unrelated to offline, but they will also allow access to push notifications for the web.

All major browers support the use of Service Workers, including Mobile Safari.  There is a know issue where service workers are [not supported on FireFox while in private mode](https://bugzilla.mozilla.org/show_bug.cgi?id=1320796)

### navigator object

There are two properties on the Navigator object that can also be useful with Offline Applications:

`navigator.online` which returns the online status of the browser.  It should be noted that "online" does not always mean connection to the internet, it can also just mean connection to some network.

`navigator.connection` is a read-only property that returns a [NetworkInformation](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation) object containing information about the applications connection.  It should be noted however, [that this property has limited browser compatibility](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection#browser_compatibility)

`windown.online` and `window.offline` can also be listened to for changes in network status

## Recommended Components

N/A

## Guidance

While discussing this topic with the other teams within the organizations, it was clear that we were not creating applications to be used offline, so the guidance below is a more community approach.

### Community Guidance

The communnity has been recommending an offline first approach when creating Web Applications by using Service Workers.  _Note that Service workers can only be used with a HTTPS connection_

There are a couple different approaches to this:

The first is to deliver all the content(html, js, css, images, etc...) from the cache first,  then load and update the from the network.

The second is the load just the header of the application, then load the rest of the content from the network.

Both approaches have a similar concept of getting something to the user quickly while the rest is being loaded in the background.

### The Cache

What things to cache are dependant on the application, but generally, you would want to cache any HTML, css and javascript files.

To store files in a Service Worker, [the cache interface is used](https://developer.mozilla.org/en-US/docs/Web/API/Cache) and they are usually long lived in memory, but how long the cache object lives is browser dependant.  It's worth noting that it us up to the developer to periodically check the cache quota using the [StorageManager.estimate()](https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/estimate)

As an alternative to the Service Worker cache, developers can also use [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) .  It should be noted that localStorage can not be used in a service worker becuase it is synchronous.

## Resources

* [Service Worker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)
* [navigator.connection](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection)
* [navigator.online](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/onLine#Specification)
