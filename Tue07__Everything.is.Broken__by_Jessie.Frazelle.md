# Everything is Broken

@jessfraz

* I worked on docker, built our entire jenkins CI
    * Linux x86
    * Power
    * Z
    * ARM
    * Windows
* Was "ops" for our apt repo
    * refactored everything from `reprepro` to `apt-frparchive` and the
      other "hardcore" debian apt tools
* TOC:
    * two stories about things broken
    * 1 with a moral lesson
    * 1 with a happy lesson Github OSS monitoring story
* Story about TLS & Zookeeper
    * no one cares, else it would be fixed by now
    * Feature complete...
    * patch made...
    * but to alpha build...
    * TLS + Zookeeper == pipe dream
    * TLS + Zookeeper == horrible options:
        * Custom build with backport
        * running an alpha release with risk of API changes
        * Neither are ideal when oyu're asking people to use your tools with a
          bring your own zookeeper cluster (it's just not easy)
* Dependencies
    * poo piles, with a bow on it
    * Gems are magic... when they work.
    * STAH(p)
    * "You don't download or improt a software dependency, you adopt it.
      Like adopting pets, it's a responsibility for the life of your
      product." - @davecheney
    * Own your dependencies.  
* Learn to admit when you're wrong.  (Or, at least with a lead kernel dev
    responds and says you're wrong, admit you're wrong.)
* Monitoring your OSS Project
    * If it's bad code, it still won't be merged.  Deal with it.
    * https://github.com/icecrime/vossibility-stack
    * monitors a github project for contributer stuff.
    * Top dream killer: Closed without merging most patches written by
      other people
