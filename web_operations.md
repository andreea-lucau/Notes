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