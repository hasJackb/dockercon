# DockerCon15 Day One

## General Session

New Docker features:

* Docker network

## Faster, Cheaper and Safer: Secure Microservice Architectures Using Docker

Adrian Cockcroft, Battery Venturs (formerly of Netflix)

* Successful modern devops = "No meetings, no tickets" getting to prod.
* Change (deploy) one thing at a time
	* Requires fast deploys
* Owning things in prod means owning cost of running it
	* Fail early and often
	* Instrument everything
	* Hypothesis-driven development
	* Efficient and autoscaled
* Docker test environments should run for seconds
* Jerry Chen, "Developer Defined Infrastructure"
* Run pentests as part of build
* Scratch base image
* Continous audit

## Reliably Shipping Containers in a Resource Reach World Using Titan

Diptanu Gon Choudhury, Netflix

Titan is a distributed compute/cluster managemnt tool. API access to all
cluster metrics. Goal is to never have to know or care where anything is
running.

cgroup notification API for monitoring/metrics. Bad hosts are killed, and
the autoscaler just brings up new ones. Autoscalers are predictive and
reactive.

Closed source, opening it up later this year. Built by 2ish developers.

