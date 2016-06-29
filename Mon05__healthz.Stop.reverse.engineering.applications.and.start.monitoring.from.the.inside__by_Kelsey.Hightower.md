# healthz: Stop reverse engineering applications and start monitoring from the inside

* How do you feel about NoOps?
* Ops says 'no' a lot.  Too frequently.
* Stop reverse engineering, and start monitoring from the inside
* You're going to write a bunch of bash reverse engineered from the app to
  stop the next outage?
* Still doing http health checks, still external checks.
* Move tests and heavy health checking inside the app at a /healthz endpoint...
* It's abstraction.  
* Ops needs to move closer to the application.
    * Could be app code, could be platform code.
    * What needs to be native in the app?
* Demo
* https://github.com/kelseyhightower/app-healthz
* Define a handler/endpoint where dev and ops collaborate to solve.
* Put strong healthchecks on everything.  Require them, and you're shielded
  from a bad deploy... Deploy will fail at canary stage.
* Demo with multiple designed failure points.  Until the last one cleared, the
  app didn't show up in the load pool.
