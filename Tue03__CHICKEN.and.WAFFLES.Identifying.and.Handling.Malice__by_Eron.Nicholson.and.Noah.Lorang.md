# CHICKEN and WAFFLES: Identifying and Handling Malice

* Basecamp is a little different...
    * not a startup, profitable since we started
    * Entirely remote, very flat
    * Own servers
    * They love nagios
* First rule of DDoS club is you don't talk about getting attacked
* 3/24/2014, quiet morning.  Start of DDoS
* All primary links at max bandwidth.
* Small attack: mesured around 80gbits/sec.
* Volumetric
* DNS Reflection, NTP Reflection, Syn floods, ICMP Floods
* Netflow allowed us to see what hit.
* We got serious about defense and mitigation.
    * Prepare for volumetric attacks.  
    * Great datacenter partner
    * Shopping:
        * Bought lots of 10g circuits and new routers
        * Arrangements with vendors to get emergency access to other mitigation
          tools
    * More serious about subtle stuff.
        * Vuln scan
        * repeated slow page requests
        * Brute force login attempts
        * Nefarious crawlers
        * etc.
    * Evaluated a handful of commercial hardware appliances.
    * Frustrated with perf, avail and weird SSL issues
    * "Supposed to fail-open"
    * No measurable protection.
* What do you actually want in a defense system?
    * Protection against app level attacks
    * Allow our actual users to keep using the application uninterupted.
    * Take advantages of all the data we have available, we know what normal
      traffic looks like.  We have auth'ed users.
    * Transparent in what gets blocked & why
    * Needs a great name: Chicken and Waffles.
    * Web App Firewall From Less Expensive Servers
    * Chicken (identifies who needs to be blocked filters)
    * its a backronym
* So what does chicken do?
    * Simple classification problem. Add ML, and you get a huristic.
    * Not so simple.
    * found known bad behaviors.
        * We don't run PHP, or wordpress.  
        * Repeated failled logins
        * Lots of ../../..
    * Request history gives us a good idea of whether someone is norma, broken
      or malicious
        * normal IP/users show normal behavior, so more likely broken rather
          than malice
        * External indicators provide us with other info than an IP
        * Facebook threat exchange.
    * We've caught more than 6,000 IPs that failed to exercise the slightest
      amount of creativity when scanning.
    * Every incoming request is scored and a per-IP aggregate score is
      calculated.  20x is work something, 40x and 50x or slow will loose points
    * Exponentially weighted moving avergage of your request scores over a time
        * Scores from 1 to infinite
        * 1.0: all requests fine
        * threshold of danger
        * threshold of block
    * False positives are real.  Need to be able to unblock.
        * Unblocks are <1%
    * Scaning for blockable actions and scoring request happens in near real-time using request byproducts.
        * Sent to kafka, and netflow, and logs, and sundry.
        * Analysis pulls from kafka
* Monitoring for volumetric attacks is relatively striaghtforward.
* Chicken provides to waffles:
    * A list of blocked
    * a list of trusted
    * A list of 'were not sure'
* What has evolved?
    * flexibility.
    * First approach: iptables on haproxy host.
        * No automation,
        * manual
        * CPU intensive
        * IP is only thing blockable.
        * CX is terrible.  Only dead-air.
    * Second: Load balancers
        * Block or ratelimit
        * API to chat
        * CPU Intensive
        * IP, user-agent, path blocks
        * CX is terrible, only dead-air.
    * Move to routers.
        * Block, bandwidth limits
        * API, auto-blocks
        * scale no problme
        * IP block
        * Cx terrible
    * WAFLES:
        * trust, block, challenge, rate limit
        * API auto blocks
        * Scale horiz
        * IP, user-agent, path
        * Friendly error message
* No waffles:
    * inet -> routers -> FW/LB -> APP
    * Waffles injects at routers to error page
    * Proxy mode waffles:
        * all traffic to waffles, and trust goes in.
        * Challenge unknown/untrusted.
    * WAFFLES lives on their own network, and traffic via BGP
    * Limited access to PROD
    * BGP Flowspecs allow us to send specific flows of traffic to WAFFLES in
      real time.
    * Flows defined by source or dest IPs
    * WAFFLES is really Redis and NGINX-openresty
        * Redis has blocked and trusted IP lists
        * Other is grey-list.  302/cookie
        * CAPTCHA, client crypto, etc.
    * Nice error message, with a link to contact support.
        * Unblocks in a few minutes.
* Lessons learned:
    1. This isn't cheap, but it beats buying a hacker a new XBox.
    2. Good data and insight into who your users are is essential to smart
       and targeted mitigation
    3. Most commercial appliances are complete black boxes.
    4. You cna build on the hsoulders of open-source giants
    5. Sometimes you just need a ton of bandwidth.
