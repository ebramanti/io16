# V8, modern JavaScript, and beyond
[![V8, modern JavaScript, and beyond](http://img.youtube.com/vi/N1swY14jiKc/0.jpg)](http://www.youtube.com/watch?v=N1swY14jiKc)

## V8's mission
> Speed up real-world performance for modern JavaScript, and enable developers to build a faster future web.

## Real-world performance
- JS Engines used to use microbenchmarks to see if they were faster version-to-version
- Disadvantage was not tuned for actual code run in web browser apps
- Static Test Suites are the current form of benchmarks, include code reflective of real-world applications
- Octane Example: PDF decode, GameBoy emulator
- Real Web Pages will be the new era of benchmarking the performance of engines
- V8 instrumented popular web pages to measure where the engine spends time loading pages
- Provides real-world Javascript improvements from measuring real pages
- Allowed V8 team to optimize commonly appearing builtins (`Object.assign`, `Object.keys`, `in` operator)

## JS Engine Upgrades
- **Orinoco**: Mostly parallel and concurrent GC with less jank, higher throughput
- 4.4 ms median GC pause on Windows M52, 4x better than M48
- Idle-time scheduling to reduce dropped frames and lower memory consumption
  * Up to 100% of GC pauses invisible on infinite scroll pages
  * Up to 50% memory savings on long-running pages
- An upcoming interpreter brings fast startup and low memory consumption, starting with low-memory devices
  * Low-memory devices especially need more lightweight code execution
  * 5-15% memory reduction in Chrome
  * Ignition: new interpreter

## ES6 and ES7
- The ES6 spec is the largest update to the language ever
- As of Chrome 52, V8 supports ES6/7! 🎉
- Why do we care about browser support for language features?
  * Polyfills and transpilers can't replicate all features
  * Less overhead
  * Easier debugging
  * Speed over time
- Demo: [https://github.com/tastejs/todomvc/tree/master/examples/vanilla-es6](https://github.com/tastejs/todomvc/tree/master/examples/vanilla-es6)

## Debugging + Node.js
- 500 Internal Server Error means you have to switch contexts
- DevTools debugs JavaScript code in V8. V8 powers Node.js. Why is it so hard to debug then?
- Pull request to allow using Chrome Dev Tools with Node.js in any Chrome window

## WebAssembly
- A new cross-browser, low-level language.
- Designed to run native C/C++ code in a tiny binary format.
- Open standard, plugin-free, no new permissions exposed
- Familiar toolchain, interops with JS
- Same browser sandbox
- Experimental suppot in Chrome, Firefox, and Edge, Chrome on Android
- Demo: [http://webassembly.github.io/demo/](http://webassembly.github.io/demo/)
