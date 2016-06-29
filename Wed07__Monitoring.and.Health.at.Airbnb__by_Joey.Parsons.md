# Monitoring and Health at Airbnb

* Fun Fact!
    * I've been on on-call rotation for more than half my life. (37yo)
* Availability is super important.
* Started with New Relic
* Datadog is primary TSDB
* instrumented with Dog_StastsD
* Very Infra-as-code
* OSS project: Interferon ###
    * Store alerts config as code ###
    * https://github.com/airbnb/interferon
    * Host_sources
    * destination
    * groups
    * objects
    * Sample:
        * Include full runbook in the alert
        * Define name
        * body of alert *also your runbook*
        * what does this alert apply to
        * who should be notified
        * what are the conditions of the alert
        * some other metadata.
    * Supports email, slack, pagerduty, and whatever else you wish to route to
* Site availability: Covered by volunteer on-call
    * What?
    * SRE focused on everyone doing on-call effectively
    * Happened randomly
    * Gong for site availabilty notices
    * Every quarter or two, teach on-call volunteers
        * Deeper into monitoring and how to be effective on-call
        * how to communicate with Customer Service
        * How to use pager-duty
    * Shadow on-call
        * Daily rotation for business hours alerts
        * Sit with the current on-call
    * promoted to being on-call
    * Weekly sysops meeting Friday afternoon
    * Go through weeks incidents
    * handoff to next on-call
    * look at metrics
    * any maintenance of the coming weeks
    * Team went to go literal Yak Shaving
* Past:
    * remediate
* Today
    * triage if you can, ask for help if you can't
* Future
    * How much is this affecting the volunteer on-call
* Harmony
    * On-Call Health
    * Are our weekly alerts trending right
    * Do we understand impact?
    * Are there false positives needing tuning?
    * are there teams that need better on-call training?
    * are the rotations and notification policies appropriate
* Measure % of alerts which are at night.
* Be a Host: It's all about people:
    * Sleep
        * Some weeks are tough.  Can your teammates 'tap out' if they're hit too
          hard?
    * Life
        * Can someone have a life?  Or are they bound to there laptops?
    * Recognition
        * Are you appropriately recognizing both on-call work and work to
          eliminate tough on-calls?
