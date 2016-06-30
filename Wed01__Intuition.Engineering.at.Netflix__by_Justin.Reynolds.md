# Intuition Engineering at Netflix
### Vizcerel Traffic Intuition

By Justin from Netflix

* Vizcerel Traffic Intuition
* Traffic & Chaos
* Traditional visualizations are for retrospective, not real time.
    * They have a delay.
* Intuition engineering
* Us-east-1, EU-west-1... until the ELB outage of 2012.
    * Christmas Eve outage.
* Started process of region reliability.
* third region: us-west-2, and user sharing between us-east-1
* Now global cloud... all users from any region
* On failover, need to scale up a region
* A bit of an art.  Knock over healthy region if you failover to quickly
* Complex system of many microservices
* "Is the region ready for more traffic?"
    * Need to know now... we need to change now.
    * Hard to reason about
    * The "now" is the far right edge of the graph
    * Must understand how the graphs fit in the infrastructure...
    * Is this important.
* Explore
    * Standard visualizations weren't working.
    * Idea of a pain suit.
    * Heart pain is customer failures.
    * Visualization wins
    * Explore graph types.
    * "Can I move more traffic? yes or no".
    * Y shaped graph.  Center is source of RPS, east/west get more... eu-west
      doesn't get as much
    * Some dots are yellow, some are red.
    * you can drill in to a region.
    * Shows all the microservices, and the traffic/ responses through them.
    * demo was sweet.
* How'd we get here.
    * WebGL for performance
    * Pixel JS to start with.  No flash
    * three.js
    * node.js
    * salp
    * atlas (from netflix)
    * OSS https://github.com/Netflix/vizceral
