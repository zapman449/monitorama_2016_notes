# Prometheus

by Brian Brazil

slides: http://www.slideshare.net/brianbrazil/prometheus-monitorama-2016

* Founder of Robust Perception, provider of Support for Prometheus
* What is prometheus
    * A time series DB
    * metrics based TSDB
    * Designed for whitebox monitoring
    * Supports labels (aka dimensions/tags)
    * Solid query language, used for graphing and alerting
* Dev history
    * Inspired by borgmon monitoring system
    * Stared in 2012 by x googlers.
    * Independent of any company
    * 250 contributers
    * Hundreds of companies
* Arch:
    * Service discovery from cloud vendors and platforms like kubernetes
    * Cassandra with JMX exporter
    * Output vizualizations with graphana
    * Defined libraries
* `pip install prometheus_client`
* Prometheous clients can export to graphite too
* Prometheous as client clearinghous.
* Power of labels:
    * Prometheous doesn't use dotted.strings like <blah>
    * Prometheous uses key=value with UTF-8
    * Can alert on any machine being down.
    * can alert on 25% of machines being down.
* Efficient
    * Single server can handle 800k samples/sec
    * New varibt encoding only uses 1.3 bytes/sample
    * Node exporter produces 7000 time series, so even wht a 10s scrape
      interval, a single prometheus could handle 10k machines
    * This efficiency means that the vast majority of users never need to worry
      about scaling
* Decentralized
    * Pull based, so easy to run
    * each team can run their own, no need for central management
    * Perfect for microsystems
* Reliable
    * A monitoring system should be something you trust when your network and
      systems are falling appart.
    * Prometheous has no external dependencies.  No complex CP clustering to go wrong.
    * For HA we keep it simple.
        * ha: run two of them, each autonomous.  Alert manager can talk to
          multiple
* Opinionated
    * as a project, we recognize our limits
    * We try to avoid reinventing the wheel (eg grafana over promdash)
    * We encourage good practices and uing the right tool for the job.  
    * Restarts on death. Don't fix it... use supervisor or daemontools or systemd
