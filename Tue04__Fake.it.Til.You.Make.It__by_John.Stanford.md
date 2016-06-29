# Fake it til You Make It

* Environment
    * several shippers -> one collector -> Elastic Search
* How to clone and scale... Can you?
* Start with onions
* Started with 7 days of logs, and analyze
* By server dominates all traffic, 96% at the controller.
* Swift generates 60% of the traffic
* Date histogram data on message rate:
    * one monster outlier (two orders of magnitude higher)
    * 99.9 at 64 messages/sec.
    * one at 1566 messages/sec.  10x per week
* Goal: generate messages along the described curve
* Now the message sizes
    * not as bad of an outlier.
    * 95% were < 240 bytes
    * largest was 782 bytes
* The cook book says
    * Find a model
    * add some noise
    * When you can't do perfect.... do meatloaf rather than Iron Chef
* Hecka has hecka flood to load test things like this. (?)
    * look at `late_bind_timestamp`
        * sets timestamps sanely, rather than process start time
    * Need better control of message contents.
    * variable message sizes didn't work
    * :-( Hecka is discontinued
* Findings:
    * Tactical
        * System sustained 4000 x 1k messages/sec
        * Collector or ES failed.
        * No messages dropped.
    * Strategic
        * Load tool is under-qualified
            * Wants to look at Adrian's Spigo
        * monitoring tool resolution is important for interpretation
        * I should prepare for presentations further in advance...
* First model:
    * Intuition 4MB/sec
    * 50messages/sec is:
        * 99.9 percentile
        * 265 controllers
        * 1060 compute
        * 1:100 ratio
    * The real answer is "The model says X is safe.  But may need to improve model"
* Next steps;
    * Make model more robust
    * find bottlenecks
    * Real world feedback
