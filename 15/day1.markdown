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

## Docker Networking

Folks from Weaveworks, Flocker & ?

Composition + Scheduling + Networking + ?

```
docker run --publish-server=service.network.weave your_net_cont
docker run -v volume_name:/data --volume-driver=flocker your_state_cont
```

Plugins can run as docker containers, or as drivers. User-installed.
You can access functionality via docker interface.

Demo of flocker and weave as plugins. Allows moving of containers + storage
across hosts while retaining dns lookups (via weave) and storage volumes
(via flocker). Actually allows stopping and destroying containers, and
then re-deploy them attached to the existing volumes, while seamlessly
moving those volumes around between hosts.

Plugins are integrated as JSON API servers listening on a unix
domain socket.

plugins-demo-2015.github.io



