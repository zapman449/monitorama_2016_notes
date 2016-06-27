# Tackling Alert Fatigue

@caitie

* "When alerts are more often false than true, the on-call's sense of urgency
  in responding to alerts is diminished.... the simple burden of alerts
  desensitizes caregivers to alarms..."
* "When alerts are more often false than true, the nurses sense of urgency
  in responding to alerts is diminished.... the simple burden of alerts
  desensitizes caregivers to alarms..."
* Nurses were alerts too frequently to heart failure... so they ignored it.
* This is a people problem, not tech problem.
* Ignored alerts -> unreliable systems -> unhappy customers
* unplanned work -> inability to complete planned work -> less time to
  focus on core business.
* Business measure this poorly.
* People problem:
    * Fatigue + Fire-fighting = burnout.
* Tackling Alert Fatigue in Hospitals
    * Increases thresholds for patients vitals
    * Only Crisis Alarms would emit audible alerts
    * Nursing staff required to tune false positive alerts.
    * _Novel Approach to Cardiac Alarm Management on Telemetry Units_  
    * THIS DECREASED FATALITIES ###
* Applied the above to Cockoo for Twitter.  50 pages per week previous.
* Started with a full alert audit.  Took 2 weeks.
* "Nothing to surface hidden assumptions like writing runbooks"
* Runbooks:
    * Table of Contents,
    * General description,
    * list of dashboards,
    * Then all the Alerts.
        * Title of alert,
        * impact to customer
            * (If no impact, candidate for alert deletion)
            * Don't page for something being weird, if there's no real impact
        * remediation steps
            * Includes customer communication
            * If you can't tell me what to do, delete the alert.
            * If you don't have control over the alert, don't alert.
* Empower the on-call
    * Tune alert thresholds
    * Disable or delete in-actionable alerts
    * Business hours only alerts are a thing.
* Weekly on-call retro:
    * Handoff ongoing issues
    * review alerts fired in the previous week
    * Schedule work to improve on-call or reliability
        * Were these actionable?
        * Did you tweak thresholds
        * do something else?
        * Prioritize fixing things
* "The goal is not to never get paged, the goal is to never get paged for
  the same thing twice" - Astrid Atkinson
* 50% reduction of alerts in 1 quarter.
    * Reductions continue after each quarter (just not as much)
* On-call slept through the night
* more time to do scheduled work while on-call
* Faster to ramp up new teammates
    * Was 6 months before on-call happened,
    * now is on-call within 1 month
* This also vastly improved the visibility into the system.
    * Quarterly pie chart of alerts by service.
* Prevention of Alert Fatigue:
    * Critical alerts need to be actionable and impacting customers.
    * Do not alert on machine specific metrics.
        * GC Pauses on one machine are not pageable.
        * High CPU on one machine is not pageable.
    * The tech lead or engineering manager should be on-call. ###
    * Cultural change.
        * move away from rewarding fire-fighting.
        * Move to preventing fires
    * The goal is ti build systems that can scale linearly with machines and sub-linearly with people.
* Benefits of tackling alert fatigue:
    * More reliable systems
    * Less unplanned work
    * happier developers.
