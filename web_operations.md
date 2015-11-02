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

## How Your Visitors Feel - User Facing Metrics
Here are the type of metrics that matter:

* web analytics - see if the visitors did what you wanted them to
* web performance
* web interaction analytics - track how visitors interact with the site
* voice of the customer - survey visitors for satisfaction

What makes a site slow?

* the time the server takes to process the request
* time spend on the network - DNS, HTTP redirects, send the request, deliver
  the response
* time spend in the browser - the time it takes to load a page is a combination
  of the number of objects, their size, the number that can be retrived
  concurently and available bandwidth

The are two ways of measuring page load delay:

* synthetic monitoring (active) - using probes

  ** it is useful when you need to know something before users sees the content
  ** useful for measuring the health of third party components

* real user monitoring (passive) - it watches visitors to a site, calculates
  the speed with which they receive the page and then generate reports
  It generates two types of reports
  ** individual visitor reports
  ** agreggate reports
  These are the steps to configure RUM:
  ** filter out unvated traffic
  ** tell the system how to track individual users
  ** tell the system how to assemble pages
  ** identifiy errors
  ** tell if what to watch for - pages, users, servers
