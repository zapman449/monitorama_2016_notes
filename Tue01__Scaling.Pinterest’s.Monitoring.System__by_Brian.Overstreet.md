# Scaling Pinterest’s Monitoring System

* Focused on scaling time-series data.
* 75+ bullion ideas categorized by people into more than 1billion boards
* Early tools: ganglia for metrics, and up/down checks for pingdom
* April 2012: 10 outages per day.  June 2012: fewer outages, but longer. :-(
* Pushed into graphite.
* StatsD -> to single graphite server
* UDP joke: you might not get it.
* 8 hours to bring up a replacement... but this setup lasted 1 year.
* Scaled by # of engineers, not # of customers.
* next gen: consitant hash of metric to backend server, by haproxy.
* UDP still a problem
* Two solutions: StatsD on each host, include hostname in metric.
    * autoscaling makes this hard.
    * Hostnames are huge in metric space.
    * ALL STATSD CLIENTS MUST BE IN SYNC.
* Sharded statsd.
    * Metric names not needed to be unique
    * Fixed most packet loss issues for a while
    * Cons: Shard mapping
* Shard out clusters... manually.
    * Complexity on each cluster? which to send to?
    * adding clusters is hard.
    * Makes greater availability.
* Graphite can't handle multiple globs per query.
* OpenTSDB based on HBase
    * Not as pretty, but far easier to query, and far faster.
* UDP is still dropping stuff.
    * Graphs are just wrong...
* "I'd give anything for a timeseries database I can trust."
* Monitoring system metrics didn't math.
* Time to replace statsd:
    * Local metrics agent
    * Kafka
    * storm
        * -> graphite or opentsdb
* Metrics-agent is the gatekeeper.
    * interface for opentsdb and statsd
    * sends metrics to kafka
    * needed to onvert to kafka pipeline with no downtime.
        * double write to existing stasd and Kafka
    * Aggregation still important.  Decided on 30 seconds.
    * More aggregate data has wins too... allows for server reboots.
* wins:
    * less gaps now
    * graphite gets 120k points/sec
    * opentsdb 1.5mil points/sec
* Statsboard
    * Define alerts and dashboards in YAML
    * Handles routing requests to various backends/clusters
* RRD data needs a fair bit of context to interpret it.
* What about opentsdb?
    * Something is wrong with my lines are often unnaturally straight.  Can
      you fix it???
* Started a user education campaign for these tools.
    * What are rrds and how to normalize
    * Metric summarization into the next interval
    * Getting request/sec from a timer
    * difference between stats and stats_counts?
    * shoudl I use hitcount or integral to calculate totals?
    * OpenTSDB:
        Getting data from continually incrementing counters
        * interpolation of data points
        * How aggregation works
        * Query optimization
* What else have we learned?
    * Protect system from clients
    * Alert on unique metrics
    * Block metrics using zookeeper
    * Including a metrics blacklist
    * Cannot control how users use the data... do not want business decisions
      off of wrong data.
    * Measuring data accuracy is hard.
        * Count metrics generated vs metrics written at every phase
        * Lots of places a metric can get lost and not known about
    * Lesson: cost of aggregation (Overhead):
    * StatsD performs network call to update, even if over localhost
    * Java uses ostrich lib for in process aggregation.
        * problem: can't get cluster level data, only instance.
    * Users need to never see the sample rate.
    * Lessen operational overhead.
        * We keep adding tools Ack!
        * more systems, = more work to monitor the monitors
        * Removing tools from prod is hard.
        * As product gains more 9s, so must metrics platform.
    * Set user expectations ###
        * Data has a lifetime, which needs to be conveyed.
        * Not magical data warehouse tools that return data instantly
        * Not all metrics will be efficient.
* Summary:
    * match the monitoring system to where the company is at
    * User ed is key to scale these tools organizationally
    * Tools scale with number of engineers, not users of site. ###
    
