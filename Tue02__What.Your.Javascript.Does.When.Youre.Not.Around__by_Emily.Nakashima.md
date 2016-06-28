# What Your Javascript Does When You're Not Around

* Browser monitoring is a thing.
* More logic moving to the browser is a problem for monitoring
* Project Dashboard 2, based around ELK
* Browser monitoring toolkit
    * Performance:
        * Page load perf
        * Statsd + grafana + google analytics
    * Exceptions
        * Capture uncaught exceptions in browser
        * Use bugsnag but plenty of other options
* JS Exceptions
    * Some helpful, some really hard to parse
    * if it's our own code, easy to parse.
    * 20-40% if youre lucky
    * A gazillion weird cases left.
* What's my JS doing? Its hanging out in a noisy room
    * Cant find module bind-all... analytics company pushed bad code.
    * Third Party code in JS is a nightmare.  Ghostery data is scary.
* It's wandered off someplace.
    * Google translate will proxy your page... including our JS code.
    * GreatFire helps do the same thing.
        * don't validate hostname to see if oyu're in production.  
* JS code doesn't show up.
    * Airports and bad wifi means the code doesn't arrive.
    * simulate at home/office.
* It's finding a new use case...
    * "Exception Class: Waking up dev"
    * you can watch what devs are doing, like looking for API Keys
    * Lots of odd exceptions can help find people probing your code/site.
* Log events, not just errors.  Info class metrics.
    * Track browser refreshes to help find pages with errors
    * Accessibility could be a great target for this monitoring.
* Lots of room for more types of perf monitoring.
* Memory leak monitoring
* Other data in the browser (now or soon)
    * If JS can see it, you can collect it.
    * Query for language, emoji support, api support, etc
* Browser monitoring is there, now.
* It's not enough though.
* FrontEnd Devs need to get paged.
* Alert on broad spectrum alerts
* front end timeouts increasing, but not backend.  FEDev needs to look.
* "The monitoring team doesn't know what the JS does"
* 
