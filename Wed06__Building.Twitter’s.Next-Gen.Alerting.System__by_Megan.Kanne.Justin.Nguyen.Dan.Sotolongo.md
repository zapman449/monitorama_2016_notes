# Building Twitter’s Next-Gen Alerting System

* Twitter has a new alerting system
* took 2 years to get here.
* @sortalongo @megankanne @justanguyen
* #talk-megan-justin-dan
* Observability team's mission:
    * Scaleable
    * Robust
    * realtime
* Not respnsible for each teams monitoring, just the system they use.
    * not the watchers on the wall
    * just the wall
* Manhattan KV Store (never heard of it)
* "Observability of Twitter" Second result on google
* 300m metrics per min -> 4.3b metrics per minute
* Old: alert -> rule -> monitor
    * The good:
        * simple config language
        * large body of examples
        * easy to write, commit, upload new alerts
    * The bad:
        * simple config language
        * large body of examples
        * easy to write, commit, upload new alerts
    * json-ish language.
    * Stapled on moustache for templating
    * Ownership of config was confusing.
        * Orphaned configs
    * Not enough effort to help people do things right.
    * alert config disjoint from dashboard config.
    * If it's important enough to alert, it's important enough to chart it
* The new system:
    * Goals:
        * Improve config
        * drop loss of visability
        * making alerts: simplicity
    * Combined alert and dashboarding.
        * Alerts are now a predicate on a dashboard.
    * New alert is written in python
        * included a shared library
        * Configs must pass tests
        * Adding server side validating
        * Make sure queries aren't too expensive
    * on-call reliability:
        * Alerts needed to come out any available zone.
        * New arch schedules fairly.
        * Alerting system time to detect improved by 30%
    * Human reasoning:
        * Monitoring isn't unit testing... it's closer to integration tests ###
        * Set an alert within context: Global, peer, and local.  any changes
          At any tier
    * Empower the humans receiving the alerts
    * Distributed systems
        * Availability and scale numbers are bigger than a single system
        * Hard to get right.
        * Hard to keep consistency
        * Structural complexity
    * Sharding is hard and important
        * Sharded by alert key.
    * rely on existing tools
        * zookeeper, manhattan KV, etc.
    * Engineering principles:
        * abstract cleanly
        * Minimize coordination
        * parallize the work
        * distribute load evenly
        * do it all FAST
    * Sharding rulesets
        * Code of honor
        * Uneven loading by sharind by ruleset
        * Solved by over-provisioning
    * User support is important.
        * UI needs to offer help
        * CLI needs to offer help
        * Config libs need comments
        * Helping out:
            * Strong validation
            * helpful error messages
            * Extensive documentation
        * Strong user guides
        * deep FAQs
        * Third line:
            * Dedicated support on-call rotation
        * User collaboration to help migration
            * Some excited to try new things
            * Some busy with other things
        * Goal wasn't to get people to migrate
            * Goal was to make twitter better.
            * Don't treat people like mules (carrots and sticks)
            * Needed a better compromise (which might mean delays in roadmap)
