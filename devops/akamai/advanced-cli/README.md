# Akamai DevOps Advanced CLI

This is Alpline based docker image (small footprint) that include Akamai Command Line Interface (CLI) with several CLI packages.

## Overview

This docker image is based on frolvlad/alpine-python3 docker image and is aimed for a lightweight image footprint. 

This container image has been built based on [frolvlad/alpine-python3](https://hub.docker.com/r/frolvlad/alpine-python3/).

**Main packages included in the image:**
- Python v3.6.6
- wget v1.19.5
- HTTPie v0.9.9
- NodeJS v8.11.4 and NPM
- Dev libraries: libffi-dev openssl-dev python3-dev
- curl v7.61.1
- bind-tools v9.12.2-P1 (dig)
- Akamai CLI 1.0.2
- Akamai edgegrid-python
- Akamai CLI packages included: 
  * property
  * property-manager (Akamai Pipeline CLI)
  * image-manager
  * cps
  * visitor-prioritization



## BUILD

This is how you can build the Docker image that will tagged "ak-devops":

```
$ docker build . --tag "ak-devops"
```


## USAGE

The Docker image contains a symbolic link /root/.edgerc that points to /root/data/.edgerc destination. You can therfore mount a persistent storage (Docker volume) to the mount point /root/data.

*Everything that will be saved in folder /root/data will be persistently kept after container is stopped.*

```
$ docker volume create alpine-data
$ docker run --mount source=alpine-data,target=/root/data -it ak-devops
```


### Prerequisites

Docker version 18 or above.


## Authors

**Pascal Maugeri** - [@PascalMaugeri](https://twitter.com/PascalMaugeri)


