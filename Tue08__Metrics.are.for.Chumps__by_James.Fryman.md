# Metrics are for Chumps
### Understanding and overcoming the roadblocks to implementing instrumentation

@jfryman

* Security practitioner scared to infrastructure
* Auth0 online identity
* mission: to enable operators to sleep
* Nashville, TN:
    * Medical industry
    * Large enterprise, hospital chains
    * Mostly .NET
    * Like waterfall
* Selfish future:
    * Want to work at places that do things correctly (tm)
    * Share success at Auth0, while sharing past failures
* Story:
    * Potential customer wanted to assert a level of capacity
        * 3500 requests per sec
        * Existing max of measured at 500 request per sec
            * Appliance offering handling 2-3x this volume at select clientes
            * Only two weeks to apply science
* Steps:
    * Recon:
        * Auth0 tried to roll out a metrics pipeline previously
        * Metrics implementation occured once in the past (librato)
        * Was ripped out because it was not well understood, thought to be
          cause of latency
    * Make the case
        * By in is no joke.  If top leaders don't care, it won't happen
    * PHOTO: HIERARCHY OF NEED
    * Can't start until we understand the retention requirements
    * We don't run a SaaS
        * Especially prevalent with on-prem software
        * Do not need to stor it yourself, make it available
        * what happens AFTER you ship the feature
        * We've made good decisions up to this point...
            * most developers have not seen a successful project - Dave Farley
            * Make decisions based on knowledge, not intuition or luck
            * 17% of projects are FATAL to companies
        * Aligning incentives:
            * IT: Decrease MTTR
            * IT: Find Bottlenecks
            * IT: Understanding seasonality for capacity planning
            * [Business] Track new feature usage
            * [Business] Track response time / page loading /engagement
            * [Business] Drive cost per unit (transaction, request, etc)
        * Have developers be on call.
            * They'll very quickly align incentives
        * Be opportunistic
            * Success is often 90% planning, 10% timing, + luck  
            * Team knew they wanted metrics
            * conflicting priorities had initial implementation over 3 months
            * Large potential customer approached, asked if we were able to
              handle specific capacity
            * Attack!
        * Pick a tool-set
            * Common pushbacks: Difficult to learn/ understand
            * Too many moving parts, concernts
            * Planning for unknown, sizing, etc
            * Doesn't even address app-level changes to codebase
            * In-house managed
                * Too many columns (gatehrers, listeners, aggregators, presenters)
            * Use SaaS... get something.
            * Auth0 toolset:
                * Datadog / homegrown
                * Logging: Kinesis -> Kibana
                * Excepiton handling Sentry
            * Iterate.
            * PDCA:
                * First cycle will be hard.
                * Phase 1 (bootstrap)
                    * Make environment
                    * measure
                    * testing
                * Phase 2 (iteration)
                    * initial testing, measure
                    * run to exaustion
                * Phase 3 (readidness)
                    * Ability to add resources etc
            * More can go wrong
                * Keep in sync with devs
                    * Change is difficult,
                    * pay attention to all feedback.
                        * "Logging is good enough"
                            * Need telemetry to narrow down events or systems
                            * assumes logging even occurs
                        * No support to interpret data
                            * failure to forget this will lead to lack of trust
                            * Finding control points was a pain
                            * Devs felt abandoned, despite early wins
                        * Troubleshooting methodology is unknown
                            * Troubleshoot at OSI model level.
                            * Help people.
                            * Build out overview of the system
                                * Even if it's ugly, horrible or rudimentry.
                                * Do yourself a favor and work on data flows
                            * Find the choke points: ELB< Nginx, App code,
                              App-aaS, mongo, db, etc)
                            * Take a Baseline measurement
                                * Start with common benchmark
                                * Agree on a common test ***
                                * don't spend time bike-shedding here on ideal baseline
                                * Throw a stick in the mud and start measuring
                                * Changes can come via PDCA cycles
                            * Isolate each component, and test individually
                            * Fix and repair
                                * Mongodb is mongodb
                                * Moved to wiredtiger
                                * Got 3x improvement. (500 to 1500 out of 3500)
                            * Accept that infrastructure will be the first question.  Deal with it. ***
                            * Keep-alives not working properly.  
                                * rewrite took 2 days.
                                * Now at 11k RPS in a single component
                            * Found slow running method in authentication code.
                                * Unbalanced CPU usage
                                * Initially tried refactor
                                * Complete rewrite removed legacy code
                            * Several discovered memory leaks
                            * Around 10k RPS.
                    * MEasure early
                    * Instrument early
                    * align incentives (use words that matter to your boss)
                    * Jump in, feet first, and iterate.
                    * Measure, twiddle, measure again.
                    * Always listen
                    * TRY TO LEAVE THINGS BETTER THAN YOU FOUND THEM
                    * Special thanks:
                        * Perf tiger team
