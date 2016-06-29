# Statistics for Engineers

@heinrichhartman (n)

* A tale of API Monitoring
1. Measure user experience
2. Determine financial implications of service degradation
3. define sensible SLA target for the dev and ops team
* First step: External monitoring
    * Configure a synthetic check
    * ensure success
    * measure latency
    * get chart.
    * Good for availability
    * alert for outage
    * Bad for measuring User Experience
    * Spike Erosion is a problem:
        * On long time ranges, aggregated / rolled-up data is commonly displayed
        * this practice "erodes" the latency spikes heavily (averages of averages)
        * Store ALL DATA and use alternative aggregation methods (min/max) to get
          the full picture
        * left side is the washed out version, right side is same, but with a max line
          drawn as well: ON PHONE
* Log Analysis:
    * Method: Write to log file:
        * tome of completeion
        * request latency,
        * other metadata
    * Discussion:
        * Rich source of info
        * easy instrumentation (printf)
        * slow, long delay (minutes) before data is indexed and becomes
          accessible for analysis
            * Massive amounts of data
        * Expensive, not feasible for high volume APIs
* Latency Mean Values:
    * Method: Select a reporting period (eg 1 min)
        * for each period, report mean latency
    * pro/con
        * measure requests by actual people
        * cheap to collect
        * ...
    * Median latency, truncated means, collect deviation measures...
* Percentile Monitoring
    * Percentile are not unique?  Use the right number
    * Method:
    * Pro/con:
        * Meaure requests by people
        * cheap to collect and monitor and graph
        * Robust to outliers
        * Up front choice of percentiles needed
        * CAN NOT BE AGGREGATED
* Percentiles can't be aggregated
    * median of two medians is not the total median.
    * If you store percentiles, you need to:
        * Keep all your data: never take a rollup
        * Store Percentiles for ALL AGGREGATION LEVELS separately
            * per node / rack / dc
            * per endpoint / service
        * store percentials for all reporting periods you are interested in (eg
            per min / hour /day)
        * store all percentiales you will ever be interested in e.g. 50, 75, 90,
            99, 99.9
* API Monitoring with Histograms
    * Storing histograms efficiently is easy.
    * Trivially aggregated across time
* The search for meaningful metrics
* Users offended per minute
    * Just count pissed off users (requests take more than 5 seconds)
    * Dont trust line graph( at least at large scale)
    * Strive for meaningful metrics

NOTE: I need to find the slides from this.  Will be posted to twitter by
handle up top
