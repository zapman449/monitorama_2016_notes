# Monitoring Challenges

### State of 2014:
* Tools need to show updates in seconds (like, 10).
* Feature Flags are a term of art.
* monitoring needs to be more available and scaleable than the thing being monitored

### What is monitoring about?

* measuring business value
* Problem dectection and analysis
* "Ultimately business value is what the business values and that is that"
* Possible values:
    * Customer happiness
    * Cost efficiency
    * safety and security and compliance
* Customer happiness: Time to value, availability, response time.
* Efficiency: High utilization, Optimized, automated
* Why isn't this solved?
* everything keeps changing (interfaces, metrics, schema, scale, ephemerality)
    * and serverless...
* Cost per node drops, revenue opportunity decreases, continuous disruption. Each generation drops the price by an order of magnitude
* Tragic quadrant.  

### Tinkering

* Simulator of large scale architectures.  spigo  github.com/adrianco/spigo
* Measuring response times in spigo (and the distribution of the same)
* Guesstimate  http://wwwgetguesstimate.com/models/1307

### Serverless
* Lambda, Cloud Functions, Azure Functions (latter are beta)
* Monitorless.
* Good for simple, single threaded code.  
* Security model is whitelisting.
* Doesn't live long enough to be exploited... Doesn't live long enough to be monitored (classically).
* Low traffic apps and super spiky apps are huge wins for serverless
* Tool for ease of ues
* Must do multi-region
* Debugging and testing are... interesting
* Monitoring (end to end tracing?)
* Using Lambda to monitor AWS
##### Challenges to running on-prem serverless:
* Scheduling and startup latency needs tackling
* execution and monitoring overhead
* how do you charge for this?
* capacity planning

### Monitoring challenges:
* Too much new stuff
* Too ephemeral (and getting more so)
* price disruption (Whats the cost model to monitor a lambda function)
