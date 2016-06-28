# Monitoring is Dead Long Live Monitoring

CTO @ http://opsee.com

In the beginning was the monitoring big 5:
* CPU: `uptime | mailx -s "cpu" admins@foo.com`
* Memory: `free | mailx -s "mem" admins@foo.com`
* disk: `(df -h; du -hs /home/*) | mailx -s "mem" admins@foo.com`
* process aliveness: `(ps -ef | grep important) | mailx -s proc root`
* ping: (blah)
* This was monitoring
* Thresholds for the threshold god:
* OK is < SOMETHING
* Orange is SOMETHING < it < something_else
* Critical it < something_else  (used salmon, not red because sysadmin PTSD)
* What asserts that something is good.  
* Fancier email, fancier math, etc.  
* Still an assertion.
* Wars: push vs pull, blackbox vs whitebox, etc.
* Change the conversation "A line in the sand"
* What is monitoring?  tangent to Observability.
* A system is observable IFF you can determine the behavior of the system based on its outputs.
    * A "System" is a set of connected components.
    * The manner in which a system acts is its behavior
    * The outputs of a system are the concrete results of its behaviors
* What is monitoring?
    * Component ....
    * One or more sensors observe the state of a component
    * an agent interprets data emitted by a sensor

## What is monitoring?
Monitoring is the action observing and checking the behavior and
outputs of a system and its components over time.

* Things change
* The problem is making assertions about data in isolation
* How do you detect a fault in a distributed systems
* The 'FLP result' [1] 1985  The general case about fault detection.  In an async network, a fault is impossible to detect.
* Byzantine Generals Problem [2]
* Big problem for us: respond to slowly or fail to respond [3][4]
    * Failing to respond is a special case of responding too slowly.
* What is required to determine if something is responding to slowly?  Service Level Objectives.
* Better health checks.  
* Monitoring is part of building the effing software.
* what if we had TDD for monitoring.  A grammer for healthchecking things at the root of your project.
* Understand how your systems behave
* build better tools: For example: Event Correlation is not a first class citizen in any tool system.

@grepory
github.com/grpory/monitorama2016
opsee.com
