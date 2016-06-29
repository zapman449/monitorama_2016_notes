# All of Your Network Monitoring is (probably) Wrong

@joedamato
packagecloud.io
@packagecloudio

* http://blog.packagecloud.io slides
* cognitive load
    * TOO MUCH STUFF to track.  Leads to high cognitive load
    * Humans have coping strategies
    * copy&paste config as coping strategy
    * "Programs should get paid more & work less" forthcoming talk
    * Do you really understand every graph you're generating?
    * (probably not)
    * if you don't understand, why do you think you can monitor?
    * (probably doens't matter though)
    * note: complexity != bad.
    * fact of life.
    * cat games bring in firewalls, and vpn and micro payments, and TLS, etc.
    * Interstate system is complex, as is tokyo subway
    * Too complicated thing? The linux network stack.
    * and... there's all kinds of bugs
    * and... really... no docs.
    * http://bit.ly/linux-networking <-- 90 pages of linux network doc
    * this is fine, if we're honest about the state of the universe.
    * List of things that don't exist
        * Free open source
        * The an singulartiy
        * cla free chocolate covered bacon
    * short version: we're effed.
    * Monitoring something requires very deep understanding
    * otherwise you're not measuring what you think you're monitoring
    * resist the urge to solve with a quick bash script
    * Monitoring requires significant investments
    * NOTHING IS FREE
    * Doesn't mean the software is bad
    * an aside:
        * time, money and business
        * engineers think they can solve by writing more software.
        * how long for you to crack the 2k pages of network doc for your driver
        * https://baremetrics.com/calculator
            * and add 35% overhead for salary
        * Doesn't matter if the stats are wrong.
        * if they matter to your business, your business will invest to figure
          it out.
        * even simple software is buggy, and hard to monitor
        * your networking monitoring is probably wrong.
