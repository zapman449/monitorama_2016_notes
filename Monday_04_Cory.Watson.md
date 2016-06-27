# Creating A Culture of Observability at Stripe

@gphat

* Stripe had problems with observability.
    * Lack of confidence, super reactive
* This isn't about tech, it's about people.
* Did it work?  see my resume at...
* Observability is a team.  3 + 1 intern
* Where to begin:
    * Spend time with the tools in place currently
    * improve them if possible
    * Replace if not possible
    * leverage past knowledge.
* Empathy and Respect:
    * People are not (generally) evil.  But they are busy.
    * Stressed, doing best with what they have
    * Being a hater is lazy
    * Help People Be Great At Their Jobs!
* Replaced existing System
    * Maybe a bad call, technically better
    * overcoming momentum is hard, adds work
    * Declaring Bankruptcy
    * Saved us ops headaches
    * still going
* Tip: Nemawashi (google it)
    * Start small, you're a great guinea pig
    * Quietly lay a foundation and gather feedback
    * ask how you can improve, follow up!
    * Engage discontent!  usually fine.  Sometimes you need whisky.
* Identify Power Users
    * Find interested parties
    * talk to them, give them what you need
    * Empower them to help others
    * watch them grow.
* Value
    * What are you improving?
    * How can you measure it?
    * is this the best way?
    * You have to think about this daily.  Success is hitting the real goal, not delivering something you're bent on delivering
* Control Theory and Observability.
    * Reference -> Programer -> System/sensor(s) -> Work
                        \----------------/
* Flat org work ethic:
    * Shave the preposterous line of yaks.
    * Stigmergy - Disperate systems working together.
    * Strike when good opportunities arise (incidents, etc)
* Advertise
    * Don't be afraid!
    * Promote accomplishments
    * Promote OTHER PEOPLE'S accomplishments
    * Humbly ask to help then learn
    * We send monthly 'State of' addresses.
* Make it easy & good
    * Much harder than it sounds.  (Email is easy, but not good)
    * Make it easy/automatic to do things right, and hard to do wrong.
* Automated Monitors:
    * Baseline monitoring
    * common problems, common solutions
    * users have no state, and are surprised
    * people care when you show them failure and how to fix it.
    * IF YOU PAGE, YOU NEED TO TELL RECIPIENT WHY.
    * Stripe built a dashboard for each alert.. including a runbook of how to
      fix it.
* Getting Feedback: how we improve
* Teach the basics:
    * Company curriculum: Teach 'em early.
    * Measuring work metrics
    * ...
    * Visualizations
* Ownership
    * Poor story for this
    * Org was ready for this, management was on board.
    * Evolving, tools are lacking.
* Did it work?
    * Yes, but not done.
        * Some teams, heck yes. Strong champions...
        * some teams, kinda the same
        * Some other teams? What is observability... why do I care? (rare)
          (Not on call)
        * Usage? Getting better.  
        * All positive feedback from automation (avg 4.5 of 5 stars) (2.5% response rate to alert feedback)
    * Tools:
        * Dozens of OSS PRs, OSS StatsD library (scala)
        * vast improvement over old pipeline, no loss
        * New styles, better nameing, more consistency
    * Adjustments
        * Embracing other tools (log analysis, error catching)
        * Begging to work on strategic things( global timers, historgrams
          and sets)
        * Need to improve metrics on our own work (we got by easy for a while)
        * Writing new monitors is super hard.  Watch for things going to
          zero too!
