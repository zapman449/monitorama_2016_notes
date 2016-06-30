# Lightening talks:

### Block Chains by Ryan
* Money takes 3 days between banks
* CC's hide this delay, but it's still there.
* Refunds still take 3 days...
    * unless you're poor
* Why does it take so long?
    * Because it's the way the system works.
    * SFTP to Mainframe is best in breed.... :-(
* Blockchain
    * Modern DB to issue and transfer digital assets
    * The data in the database is the money.
    * Each transaction has three pieces:
        * Values
        * Logic
        * Auth
        * auth'd all the way down.

### Data-driven DevOps by Stella
@stella_udo
* CAMS: Culture Automation Measurement Sharing ###
* Measurements:
    * What should you measure?
    * DevOps Report 2016
    * High performing teams perform 200x faster
    * Don't measure activities
    * measure outputs/outcomes
    * Monthly Active Users
    * Might Matter Metrics:
        * What are YOUR metrics that matter?
        * They may change... week to week, and between teams, etc.
    * It is all machine data.
        * Everyone gets access to the machine data
    * Visibility across the whole dev lifecycle
    * Use machine data to increase app velocity
    * Use machine data to manage testing and QA
    * Release when you have good code, not on a specific day
    * Use MD to drive CImprovement
    * Practice Empathy with Data Driven Insight
    * Real examples
    * relax and enjoy your journey

### Manifest Pareidolia by Dave
* Taxonomy of monitoring tools (a monitoring of a taxonomy)
* Drawing of iconic images into graphs.  
* Beaker on a curve
* Excite Bike climbing a spike
* Silver surfer on a stack graph wave

### Don't believe the data : Data vs intuition by Aaron
* Processing Data and making a decision
* 2.5 quintillion bytes of data per day.
* Brains hold 3tb ... 1 millionth of data per day on net
* Take a deep breath
    * P1: food and water
    * P2: Survive today.  Likely something is chasing me.
    * P3: Find someone special
    * repeat.
* Hello frontal lobe
* Building your own github/runbook every day.
* National Weather Service knows humans over programatic forecast improves
  forecast.

### Tech Community Psychologist <-- made up title just now
* I'm the tech recruiter
* #stalker
* OSS Life Lessons:
    * Video of her singing to a piñata whale.
    * Taylor swift as though leader ???
        * Girl, guitar, and autotune.  
        * Start where you're comfortable.
    * Bring your friends.
    * Don't showboat.
        * entire company doesn't rest on your shoulders. ###
    * Knowledge Share
    * Don't be afraid of Haters (get drunk on their jealousy)
    * Do you.
        * If they don't like you for being yourself, be yourself even more.

### Dyn DNS
* Monitoring the macro internet for network outages.  Cool stuff

### Exploring Site Reliability principles with games by justin Dugger
* Responsible for uptime
* Hanabi good game to model
* P = Principle
* P1: Provide actionable alerts
* P2: Hunt Single Points of Failure
* P3: Blameless postmortems
* Principle lazy8: Write your own story
* No one has the full story.

### Spam Management and demand control in monitoring systems By Scott Franklin
* Growth of metrics is a thing
* < 1% of data is queried
* Non queried data can still be valuable
* Slicing during debugging
* data often only useful during outages
* Some data is terrible in datastores
* facebook system:
    * No registration
        * only require tag with team name
    * restrict only to keep system healthy
    * audit after the fact
* Protect the system from users
* Protect users from each other.
* track resource usage per team
    * teams can raise their own limits
* system floats up new metrics.  And generates a regex which matches all of them.
* (track things which are read, vs not read)
* 3 clicks and your new metric is blacklisted.
* Big spike, low priority alert.  Bigger spike, on-call alert.
* Cut growth by 60%
* Didn't get in the way of people doing their job.  Didn't stop honest players.

### Shmarallel, Shmostulate By Dan Slimmon
@danslimmon
* Euclid proved a bunch of stuff about geometry
* Or that's what he thought.
* A postulate is something you know to be true.
* 4 postulates gave 28 theorums, but not the 29th
* 2000 years to fix the 5th postulate
* Non-euclidian geometry solved 5th postulate. Euclidian is first 4.
* Math isn't about picking real objects and studying them
* You choose the definitions you WANT and study the results. ###

### The benefits of a systems lens by Jason Hand
@jasonhand
* Viewing feedback from a "systems thinking" model
* Research in bias
* System: interacting or interdependent components for a complex 'whole'
* Feedback: Giving  and receiving
* Systems thinking:
* Correct the skew of any single perspective
* 5 benefits:
    * Accuracy
    * Judgement
        * Discard needless judgement
    * Enhance accountability & Responsibility
    * avoid blame
    * Avoid fixes that fail (temp fixes)
* 3 questions:
    * Difference between giver and receiver
    * Ask what is the roll?
    * Are process or policies causing friction to feedback?

### Hosted Graphite By Charlie
* Protect your lizard brain from on-call
* Amazon burns people out like "little tea lights"
* Let's not follow that example
* 5 things:
    * Hire more people
    * Pay attention to unused holiday days.  Consider forcing people to
      take breaks
    * Encourage evening and weekend disconnections
        * Don't work more hours than needed.
    * Best effort on-call support for (New Feature) (or business hours)
    * Our on-call shifts are weekly... end on Friday morning, and you get
      the rest of the day off.
        * tried as an experiment, works very well
        * Quotes:
            * "Makes on-call almost bearable"
            * "Allows for a clean break before your weekend"
            * "Friday morning sleep in allows for healthy weekend"
        * Scales with team size... cheaper as team grows
        * Hiring benefits.
    * Manager on-call: Does it blind manager to forest level issues if they're
      feeling the pain of the trees?
        * manager with no on-call experience is probably worse though.
