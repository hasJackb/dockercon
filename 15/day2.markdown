# DockerCon15 Day Two

## General Session

Today focuses on orchestration.

### Business Insider DevOps

Lessons learned:

* Build local first, then production
* Porting backwards to to devs is bottleneck.

Moved to using Fig. Allowed rapid setup of dev envs. For multi-host prod,
moved to using upstart for management, but it was a pain.

Eventually settled on deploying with Puppet+Docker module.

### Docker Product

Focus on Docker Hub

* Security
	* Authentication microservice
	* one-time build hosts
	* security audits
* New UI
	* Much more streamlined, minimalist
	* Public beta out now at hub-beta.docker.com
	* 5 free private repos w/coupon code dockercon2015

General Demands
	* support
	* on-premise registry
	* networking

New product: Docker Trusted Registry
	* On-prem
	* LDAP/Active Directory integration
	* Role-based access control
	* Audit & events logging
	* Easy deploy, upgrade, rollback

### GSA

Moving monoliths to Docker, running the trusted registry via Booze Allen Hamilton.
Using HAProxy Interlock for dynamic load balancing as containers come up and down.

Next Steps
* Inserting secrets into containers with Keywhiz
* Plugins for Interlock
* API for Interlock

### Commercial Offering

Subscription
	* Docker engines, image registry, support
	* Num. engines x support levels = price
	* $150/month for 10 engines

### Microsoft Bullshit

No point.

### Project Orca

Top to bottom orchestrated stack. Orcha is the answer to the 'run' of the
build ship run cycle.

## Docker Security

Nathan McCauley & Diogo Monica, Docker

Limit capabilities of containers via:
* AppArmor/SELinux
* Syscalls
* Namespacing
* ulimits

Working on support for a security manifest which can be shipped with the
container (maybe baked into the image?) so that all containers run with
the same limits, and they're transparent.

dockerbench.com is a security audit tool shipped as a docker container.

Docker is on the path to least-privilege microservice support. Right now
it has a bunch of little knobs for config, but it's getting easier and
more unified.

## Lunch

Talked to the guys from convergeio.com again about their distributed FS. Saw
their demo with Michael. Would be interesting to try to combine them with
Flocker.

## Scaling New Services: From Container Creation to Automated Deployments

Brian Scott & Patrick O'Connor, The Walt Disney Company

Using Mesos + Marathon + Docker for BI clusters. Builds on Jenkins. No info
regarding how they handle CI testing.

## Container Hacks and Fun Images

Jessie Frazelle, Docker

Really cool. Runs almost everything in containers, including pulseaudio, Skype,
Tor, GIMP, etc. Basically everything other than a terminal. Seems to run i3wm.

Wraps all the docker stuff into bash functions so programs can be started from
the CLI like you'd expect. Apparently rather challenging to get this stuff
working. Dotfiles are open-sourced.

Talk of contributing the Tor hack as a Docker networking plugin.

## Running Aground: Debugging Docker in Production

Bryan Cantrill, CTO Joyent

Great talk, very funny. Covering types of failure and modes of debugging.
Basic tenet: fail fatally whenever possible, always core dump, and only
then consider restarting the container.

Consider 'just restart the container' equivalent to 'just reboot the computer'.
Avoid it.

