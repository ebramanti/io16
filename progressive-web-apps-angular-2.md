# Angular 2 and Progressive Web Apps
[![Mythbusting HTTPS](http://img.youtube.com/vi/vAb-2d1vcg8/0.jpg)](http://www.youtube.com/watch?v=vAb-2d1vcg8)

## The Web
- Web 1.0 - Synchronous
- Web 2.0 - Single Page Apps, Ajax
- Angular - What HTML would have been if designed now
- Single Page Apps Today - lots of code pushed to the browser

## Progressive Web - An App-Like User Experience
- Angular is evolving with the web
- How hard is it to make a web app immersive?
### Application Shell
- First thing sent to the phone
- Tells user the application is alive
- Put script tags at bottom to load code asynchronously
- Declarative Application shell - shell render directive for loading screens
### Architecture
- Angular handles talking to the DOM for you, but not decoupled
- Angular 2 has a separate renderer and application library
- Angular Universal: allows Angular to be treated "like an app"
- In Gulp, booting up app and prerendering content, writing it out to disk
- Allows for static caching of app
- Initial rendering can also happen at runtime on a Node.js server (or others)
- Server rendering benefits - performance, SEO, stability
- Service workers provide enhancements to a progressive web app
- When a user opens an app, static content and app shell make things load quickly
### Lazy Loading routes
- Don't load code you don't need
- Too much code is slow to load, handled with lazy routes
- Lazy routes load the code needed
- Code loaded dynamically to keep app running
- Service workers can load the lazy routes into the cache so the app is faster

### Data Binding
- Bind with components to get data
- Use change detection to detect changes in the data

### Template Compilation
- Building apps for speed requires compiled templates
- To compile Angular 1, go from xhr -> parser -> dom -> Angular 1
- In Angular 2, template -> parser -> AST -> Source(JS)
- So it's just source -> browser, which compresses the code
- Hello World Angular1 to Angular2: 118KB -> 22KB

### Plays well with others
- Firebase: works really well with Angular
- AngularFire2 for Angular 2: real-time chat in 8 lines of code for example
- Push messaging with Firebase works great for Progressive Web Apps
- Web Components: able to easily integrate with things like YouTube

### Angular CLI
- Focus on your app, not the tools
- `ng new my-web-app` - sets up everything you need
- `ng serve` watches file system and refreshes the browser
- Progressive tools out of the box:
  * `ng new my-web-app --mobile`
  * `ng-serve` will set up everything with the build process

### Multithreaded Web Apps
- No, really.
- Web Workers
  * UI Thread - DOM, Angular
  * Worker Thread - process images, etc.
- Angular 2 - same UI thread, Angular 2 in Worker thread
- Without web worker - do work, do work, render, paint
- With web worker - do work and render at the same time

### This is just the beginning for Angular 2.
- See Issue Zero example - [github.com/angular/issue-zero](github.com/angular/issue-zero)
