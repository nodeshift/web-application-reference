# Offline

* Short overview of what offline is according to the Ref ARch
  * could also be "crappy connnectivity" (Lie Fi)

* Web App (PWA) vs. Native app?

offline first? - community approach?
  * deliver all content from cache first,  then load from network
  * deliver header from cache, then load content from network

* The different options for web and offline -
  * Service Workers
  * App cache - deprecated in chrome
    * Different platform support
    * https://caniuse.com/online-status
    * https://caniuse.com/serviceworkers

  * navigator.online - returns the online status of the browser
    * gotcha is ...

  * navigator.connection - returns a NetworkInformation object
    * Limited availability. No FF, Safari/mobile

  * Others?

  * What to cache?
    * just html, css, js?
    * anything else?

  * tips for loading a page in a bad network?
  * display a ui template first, while loading?



  * local storage reset timings on browsers?
  * indexDB
  * What to use for service workers to store the cache
    - is this to much detail


## Recommended Components

N/A

## Guidance

* Do we have any teams that


## Resources

* https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API
* https://developer.mozilla.org/en-US/docs/Web/API/Navigator/connection
* https://developer.mozilla.org/en-US/docs/Web/API/Navigator/onLine#Specification
