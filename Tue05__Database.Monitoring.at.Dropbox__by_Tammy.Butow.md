# Database Monitoring at Dropbox

@tammybutow

* Internet is safe compared to going outside... in Australia (maybe)
    * Yahoo is cool, until about 2000... in Australia
    * train tracks melted.
    * shoes melt
    * sunburn.
    * So moved to USA.
* I like monitoring
    * Achieving any goal requires honest and regular monitoring of your progress
    * Apps:
        * Hopper
        * Cool ideas from health and travel
    * Dropbox is cool
* Scaling to exabytes and beyond
* Monitoring
    * Start:
        * Nagios, Thurk (?), Ganglia
    * Vortex (home built)
    * Logging, we built droplog.
    * Why build our own?
        * Performance
        * Reliability
        * scaling the number of metrics/sec very fast
        * as we grew, new features fast.
    * Vortex customer built TSDB with dashboarding
    * Metric Metadata: Tagging for metrics
    * Databases team requested 'snooze button' from the host leve.
    * Monthra: third party metrics into Vortex
    * 5000 MySQL ... monthra get metrics beats cron.
* Databases monitoring at Dropbox.  
    * Monitoring DBs is reactive and proactive:
        * Proactive:
            * Whenever there's a spike, we get a page
            * talk to service owner to understand change
            * We know it's not MySQL running hot.
        * Reactive:
            * Still happens
    * Service is running on an actual server.
        * Dashboards in team charter (which is public?)
        * DB Ops Bot
        * Scout: Insight into pager duty data
    * CPU memory, network, disk (IO and space)
    * Dashboards
    * Service metrics
        * What are your durability goals
        * Reliability goals
        * how do you align?
    * Graphana
    * Threads Running vs Threads Connected ###
    * Workload Monitoring
        * Num queries fired, by type
        * TCP Profiling
        * Top queries
    * Fake shareds and fake DBs
* Simple monitoring:
    * only two lines on most dashboards
    * only show one graph at a time
* Incident Manager is a pattern.  Managers/senior managers on rotation
  for serious incidents
* OpsLog pattern in chat.  person looking acks in chat, and says what
  they're doing
* They have blame and commmit history for all alerting tweaks.  Threashold,
  blame, etc.
* Alert for DBs at 90% of disk
* Bots in slack
    * Talk to ourselves to keep track of train of thoughs
* Encouraged to delete and modify alerts
* Everyone can edit alerts
* They do DRI: Directly Responsible Individual.
* "Its all about figuring out the right balance so you don't get paged
  repeatedly."
* Once a week, take 30min to choose 2-3 actions you can do to reduce alerts.
    * Look at top 5 most frequent alerts in last week.
    * drug from pager duty API
* Daily KPI Email reports
    * Daily summary sent via email
    * reply-all when there's an issue
    * a rolled up email to all of infra org each day.
* Monthly metrics review
    * Get together to review metrics
    * set action items and goals for next month
    * about people and tech
    * measurement is our culture #sweatthedetails and #aimhigher
* Hardware checkup for bare metal servers
* No server hugging
    * Hosts are all replaceable (auto_replace.py)
    * Auto replace all the time
* Disaster Recovery Testing
    * Testing tools: Chaos Monkey and Chaos Kong
    * GameDays or DiRTs "What do we want to break today?"
* The future:
    * If you're on-call, monitoring should show you immediately what spiked
    * Interested in ML
    * big dreams

### TL;DR:
* What you can do with a team dedicated to DB Dashboarding. :-(
* Custom tool for monitoring
