# Web Operations

## Monitoring

Availability = Update / (Uptime + Downtime)

Availability is influenced by 4 parameters:

* MTTD - mean time to diagnose
* MTTR - mean time to repair
* MTTF - mean time to failure
* MTBF - mean time between failures

Increase availability by reducing MTTD and MTTR and proactively increasing MTTF.

Don't use production systems for monitoring - the monitoring should be done on
a separate, management network.

Things to look out for when monitoring a system:
* availability
* functionality
* quality
* context
* credibility

## Dealing with Traffic Spikes

Reactive cache can be dangerous - you will have a spike in cache miss when the
entry expires.

Lessons learned:

* plan for 5 years ahead
* load test the production system
* think about the whole stack(both software and hardware) and rethink the whole
  application if needed

## Dev ond Ops Collaboration and Cooperation

If devs and ops are completely separated, they will not be able to help
eachother and share information. Share responsability for reliability produces
better results.If devs also have an oncall rotation, they are more incentives
to think about reliability.

Advises for optimizing the deployment process:

* the build and deployment should be repeatable and fully automated
* have a good staging environment
* make deployment as fast as possible - the order of minutes

Example of tools that can be shared between devs and ops:

* live debugging tools - the extra information needed by a dev when building a
  system is often the same needed by an ops when debugging the live system
* feature flags
