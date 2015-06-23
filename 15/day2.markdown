# DockerCon15 Day Two

## Key Note

Today focuses on orchestration.

## Business Insider DevOps

Lessons learned:

* Build local first, then production
* Porting backwards to to devs is bottleneck.

Moved to using Fig. Allowed rapid setup of dev envs. For multi-host prod,
moved to using upstart for management, but it was a pain.

Eventually settled on deploying with Puppet+Docker module.

##

Focus on Docker Hub

* Security
	* Authentication microservice
	* one-time build hosts
	* security audits
* New UI
	* Much more streamlined, minimalist
	* Public beta out now at hub-beta.docker.com
	* 5 free private repos w/coupon code dockercon2015

## Docker Product

Demands
	* support
	* on-premise registry
	* networking
	*

New product: Docker Trusted Registry
	* On-prem
	* LDAP/Active Directory integration
	* Role-based access control
	* Audit & events logging
	* Easy deploy, upgrade, rollback

## GSA

Moving monoliths to Docker, running the trusted registry via Booze Allen Hamilton.
Using HAProxy Interlock for dynamic load balancing as containers come up and down.

Next Steps
* Inserting secrets into containers with Keywhiz
* Plugins for Interlock
* API for Interlock

## Commercial Offering

Subscription
	* Docker engines, image registry, support
	* Num. engines x support levels = price
	* $150/month for 10 engines

## Microsoft Bullshit

No point.

## Project Orca

Top to bottom orchestrated stack. Orcha is the answer to the 'run' of the
build ship run cycle.

# Docker Security

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
