# Polymer and Progressive Web Apps: Building on the modern web
[![Mythbusting HTTPS](http://img.youtube.com/vi/fFF2Yup2dMM/0.jpg)](http://www.youtube.com/watch?v=fFF2Yup2dMM)


## Polymer's Mission
- Provide tools and libraries for using the latest web platoform features to build progressive web apps.
- Simple mission: **Use the platform** to deliver **great user experiences**.

## HTML
- Lowest level primitives for designing UI
- Difficult for non-document markup
- JavaScript has become an escape hatch to solve this problem
- Has worked for desktop, but things have changed with mobile web
- Slow loading apps don't work on mobile, will create user frustration
- Less JavaScript is the solution, use what is already there in the user's browser
- New features coming to the web allows for engaging, immersive, app-like experiences with browser features.

## Using Web Components
- We want browser to be more capable by formalizing the component.
- There are a million frameworks to choose from
- Nevertheless, frameworks can provide useful structural features
- There is a cost of this abstraction
  * Have to send JS to provide the meta-platform (fine on desktop, slow on mobile with slow connection)
  * Components for different frameworks can't mix and match.
- The promise of web components: native component in the web platform itself
- Web components allow you to extend the language of HTML, no framework overhead cost
- Every framework has to speak HTML, so components now can be used in multiple frameworks
- JS stack no longer matters with web components
- Draft of web components by W3C presented in May 2012, almost finalized
- **Template elements, HTML Imports, Custom Elements and the Shadow DOM** is being worked on from major browser vendors
- [customelements.io](customelements.io) - 2000 components
- Broad native web component browser support is no longer a matter of if, but a matter of when (could be later this year).

## Building Web Components
- Polymer makes it easier to use the bold features above of web components.
- Polymer needs to be faster, biggest complaint
- Polymer 1.0 released at I/O 2015, much faster than Dev Preview (~4x faster)
- Polymer performance has continued to improve past 1.0
- Polymer is one of the fastest growing front-end technologies at Google
- ~400 projects at Google are using Polymer
- Polymer in production with many apps (YouTube Gaming, Translate, Play Music)
- Polymer also used outside of Google (4 million webpages on open web using it)
- The Polymer Library is for building components

## Building Apps (specifically, Progressive Web Apps)
- Use what the browser gives you to build great apps.
- Minimal payload, overhead, offline-first
- Polymer App Toolbox: announced at talk
- Includes layout, routing, localization, storage, and CLI

### Layout
- App-layout elements: helps to construct mobile app elements
- Toolbars, drawers and headers
- Responsive
- "Fancy scroll behaviors" are included

### Routing
- Need: modular, idiomatic routing
- `<app-route>` component
- Path property will match on the route
- Flexible, modular, composable

### Localization
- Need: modular, idiomatic localization
- `app-localize-behavior` - uses the platform

### Storage
- Need: turnkey data integration
- How do I connect data to my app?
- `<app-storage>` - interface to connect to a service
- Turn-key data integration with idiomatic data binding
- Properties, events, and data-binding in `<app-storage>`
- Can connect a cloud and local storage component together

### CLI
- `polymer serve` - serves your components
- `polymer lint` - looks for common errors
- `polymer build` - adds main entry point, and bundled/unbundled directories


## Delivering Apps
- How do we deliver an app without a splash screen?
- Web components, HTTP/2, Server Push, Service Worker
