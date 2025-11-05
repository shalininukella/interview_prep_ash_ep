---
icon: docker
---

# Docker

#### Refer this - very nice roadmap

{% embed url="https://roadmap.sh/docker" %}

#### What is it ?

Engine that creates containers. Containers are just a set of linux processes that has its own filesystem and resource access constraints via linux namespaces, cgroups and device permissions.

#### Container States

**Created -** Just created from image, never run.

**Restarting -** booting up

**Running -** booted up

**Paused -** All processes stopped

**Exited** - Ran and completed

#### Networks

**none**

Isolate the container completely.

**host**

Remove the network isolation from container completely.

**Bridge**

* A bridge is a link layer between two networks which can be software defined or hardware
* A default bridge named `bridge` is already created when docker is started and by default all containers join this bridge
* Users can also create a bridge network which also allows a DNS resolution between containers
* Containers can be attached / detached on the fly from user defined bridges
* `docker network connect <this-container> <to-this-network>`

**overlay**

* Connect multiple networks across a docker swarm with each other

**ipvlan**

* L3 network access

**macvlan**

* L2 network access
* Doesnt work unless promiscuous mode is allowed

#### Commands to remember

**run** - creates a container and runs a command in it ( remember that unless --rm is specified it will not delete the container on exit )

**create -** just creates a container from an image in a created state

**start -** starts a paused container

**images -** show pulled / created images

**ps** - show running containers

**build -** build image from a Dockerfile

**tag -** tag a built image

**logs -** show logs of a container

**exec** - run a command on a running container

**network connect -** connect container to network

**volume ls -** show volumes

**volume create -** creates a named volume owned by docker
