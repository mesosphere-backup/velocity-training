# Container & Docker 101

There are a few [valuable Docker](http://www.nkode.io/2014/08/24/valuable-docker-links.html) links out there.

## Setup

Make sure you have your DCOS cluster per team up and running. Then do:

    # add key once:
    ssh-add ~/.ssh/mesosphere-training-aws
    # log in with forwarding enabled (so that you can log in from master to one of the agents)
    ssh -A core@MASTER_IP_ADDRESS

We will carry out the following tasks on the Mesos master instance of the DCOS. It is a [CoreOS](https://coreos.com/) environment, so Docker native.

If you have issues sshing into the Master, check out https://docs.mesosphere.com/services/sshcluster/ or ask for help.

## find and run
    
    $ docker run -it 
    $ docker run -d
    $ docker ps -a
    $ docker ps -l
    $ docker images
    $ docker search ubuntu
    $ docker run -t -i ubuntu:14.04 /bin/bash

## build

    $ mkdir -p mh9test/nginx
    $ cd mh9test/nginx
    $ touch Dockerfile
    $ echo > Dockerfile <<EOF
    FROM nginx
    MAINTAINER Michael Hausenblas <michael.hausenblas@mesosphere.io>
    RUN apt-get update && apt-get install -y git
    RUN echo "I just built my first Docker image \o/" >> /usr/share/nginx/html/index.html
    EOF
    $ docker build -t mh9test/nginx:v2 .
    $ docker run -d -p 8081:80 mh9test/nginx:v2

## pull and push

    $ docker pull ubuntu:latest

Make sure the repo exists under your account, say https://hub.docker.com/u/mhausenblas/ and then:
    
    $ docker images
    REPOSITORY             TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
    m-shop-app             latest              5891be3406d7        19 hours ago        349.8 MB
    ...
    $ docker tag 5891be3406d7 mhausenblas/m-shop-app 
    $ docker push mhausenblas/m-shop-app

## introspection 

    docker exec -it $CONTAINER_ID sh
    docker logs $CONTAINER_ID
    docker inspect $CONTAINER_ID

## clean up

    $ docker rm -v $(docker ps -a -q -f status=exited)
    $ docker rmi $(docker images -f "dangling=true" -q)
