# How to Teach an Old Monitoring System New Tricks

@beerops

* _Effective DevOps_ co-author
    * day in the life of a systems engineer
        * http://bit.ly/yaynagios
        1. Wake up and smell the new servers
            * 5 years ago, the worst. Hand crafted nagios configs per server
            * Now, deployinator
            * Use chef as source of truth for who should be in nagios
            * Auto host groups by chef-roles
            * try-nagios https://github.com/etsy/TryLib
                * Config needs to be valid in all datacenters.
            * nagios-validate
                * Warning for 'no contact_groups'
                * Encourage people to set their own.
            * Deploy hosts, regardless of being ready for nagios
                * wired into deployinator, to make sure things are deployed...
                * and they start in downtime.
                * meaning scheduled downtime
                * notice into IRC, leave downtime at noon eastern tomorrow
                * Warning when downtime expires in a few minutes.
            * perfnag
                * Performance alerts, recommended warning and critical
                  thresholds
                * Autogenerates the nagios config.
        2. Making Alerts (marginally) less annoying
            * nagdash (OSS in github)
                * Great, but all org, not just my team
            * nagios-herald https://github.com/etsy/nagios-herald
                * Add context to nagios alerts.
                * Includes problematic volume,
                * ganglia graph,
                * threshold exceeded
                * How often has this happened recently.
                * ruby gem
            * Telegram, new custom templater and recipient control
                * Subscribe you to certain alerts
        3. Tackling those Zzzzzz
            * opsweekly https://github.com/etsy/opsweekly
                * generate on call reports.
                * was it actionable?  If not, why?
                * Track sleep failure events.
                * Per user reports about alerts received.
                * Per team reports about alerts received.
        4. An on-call bedtime story
            * Want to know if something will wake me up.
            * Emails the on-call at 5:00PM local
            * Here's everything which is not OK, and in scheduled downtime, and
              downtime expires in 24 hours.
            * Awesome.
            * Allows for preventing late night insane alerts.
    * Nagios is good at running checks
    * we can decide how to make it's check results the most useful to us
    * all about customization
    * Always needs iteration and improvement
    * More new tricks to discover
    * Nothing is 100% perfect out of the box
    * Focus on composability, pluggability, and customizability.

Related talk: https://speakerdeck.com/kdaniels/leveling-up-monitoring-a-decade-of-automating-and-scaling-nagios
