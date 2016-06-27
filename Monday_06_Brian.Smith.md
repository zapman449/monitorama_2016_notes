# The Art of Performance Monitoring

* High Cardinality Alarms
    * Where 100 instances all page you all at once.
* Reactive Alarms
    * Fired for conditions which no longer exist, and are no longer relevant
    * Cause:
        * One day, you have a huge issue
        * incident response meeting, solution: create a new alarm.
        * multiply by 2 years...
        * and you start ignoring it.
    * Don't be afraid to delete actions.
* Tool fatigue
    * too many or too few tools.
    * too few leads to the bash one-liner
    * too many leads to the on-call run-book
* Commonalities: Mechanical, Simple and Obvious
* At each step, it is the most rational thing.  ###
* Scribe, a distributed message bus.
    * Logs, metrics events go in
    * PTail (Parallel Tail) is the output engine.
    * needed to know if they were reading up to date message, or something from
      a backlog.
    * Need to Measure Specifically.
    * Produced a new gage to measure the back-pressure: 1 or 0.  If too many
      readings of `1` too close together, you're not reading fast enough.
    * Vague metrics mean its hard to write automation.
    * Time series math metrics and tools are still infancy.
* Key components of good alarms:
    * Signal
    * Actionability
    * Relevancy  (akin to entropy.  If this increases, bad stuff happens)
    * Two kinds of alarms: processed by machines and processed by humans
    * Machines can deal with millions of machine alerts.  Humans can't.
    * Focus on improving actionability on your alerts.
        * Nuked ambiguous alarms.  The system will give us feedback by breaking
          in ways we wouldn't know.  So nuking isn't the end of the world.
    * Then they improved relevance.
        * Forced down to one alarm for each layer of the system
        * Then alerts allowed you to ignore anything above the lowest level alert.
    * Your dashboard is your debugger. ###
    * Cubism: A stack of time series graph.  Every time a bar goes over a range,
      darken the hue of the bar.  Allows for drill down
* Summary:
    * Have specific metrics
    * Your dashboard is your debugger
    * Minimize necessary attention
    * Use high level alarms.
* Q&A:
    * Measure accuracy of alarms.  If 90% it's nusiance alert, figure out
      why.     
