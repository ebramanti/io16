# Fast and resilient web apps: Tools and techniques for delivering great user experiences
Why carving out the "fast path" is not enough

## Resilient
- Pattern seen in many teams: Follow good practices, made app fast, but the app is still slow on some devices
- Many issues devs face, but asking wrong questions
- "You made it fast, but you did not make it resilient"
- resilience - tolerant to fault
- Resilient to: limited carrier capacity, network throttling, routing issues, thermal throttling, memory pressure

## "Fast" is not enough
- Fast devices are often slow
- Fast networks are often slow
- Variability makes everything slow
- Still possible to build **resilient** apps that deliver great UI experiences

## Evolution of performance
- Damage control: performance **is** a bug
- Robustness: performance **is** a feature
- Performance **is** resilience

### Performance is a bug
- Performance notable by absence (tech debt, users complaining, PMs angry)
- Performance is a fire drill when things are broken
- Performance "fixed" after a fact (as much as you can fix a faulty foundation)

### Performance is a feature
- Performance is a criteria at all stages
  * UX -> development -> Production
- Performance is a continuous process
  * Monitoring -> Learning -> Improvement
- This process set us on a path towards **robustness**.
- Robustness playbook
  * Build processes to catch human failures (code review, best practices)
  * Build processes to prevent accidental failures (test suites, regression detection, canary rollouts)
  * Add redundancy into the system (duplicate data, compute, infra)
  * Add processes to prevent propagation of failure (rollbacks)
  * Recognize that dealing with failure is part of the design (simulate failures in dev/prod)
- Reduce number of critical resources to improve performance of the app
- Robustness is necessary but not sufficient.
- We cannot squash all variability or fix what we don't control.
- Lessons from the Google Search team
  * Many systems can tolerate inexact results
  * Proactively abandon slow subsystems
  * Use dynamic cutoffs
- It is possible to build a resilient whole out of unreliable and misbehaving parts!
- Sources of variability - expanding range of performance due to developing markets
- Low battery, overheating, and background processes cause variability in web app performance

## Axioms of a resilient app
- Performance is not a static characteristic
- Fast devices are often pretty slow
- The dynamic range of performance is increasing

## How to improve performance?
- Offline is the norm, not the exception
  * Client must be able to render the app regardless of connectivity
  * ServiceWorker is an option
- Provide a fallback for **every request**
  * No request is "too important" to fail
- Assess and adapt to the client's state
  * Cores, battery status, data savings mode, network type, screen size
- Monitor, measure, and adapt again
  * Properties of network fetch, 60FPS target, adapt at runtime are some things that lend themselves to this approach