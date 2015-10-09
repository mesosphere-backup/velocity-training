# Mesos and Marathon 101

Keep https://mesosphere.github.io/marathon/docs/ open in a browser, you'll need it.


## Launching apps via the Marathon UI 

- Got to DCOS dashboard
- In the Marathon UI
 - Start simple app such as `while [ true ] ; do echo "Hello DCOS" ; sleep 5 ; done`
 - Scale up and down
 - Make yourself familiar with health checks 
 - Start a Docker app (hint: use one from the previous session on Docker)

## Launching apps via Marathon HTTP API

Note that we will use [HTTPie](http://httpie.org) in the following but you can use `curl` should you wish to do that.

    http POST http://mh9-dm-in-elasticl-8o235kczv1jx-1273189503.us-west-2.elb.amazonaws.com/service/marathon/v2/apps < marathon-hello-world.json

There are a few more sample app specs here in this directory, such as `marathon-peek.json`. Play around. Try the same things you did before in the UI now via the HTTP API.

## List apps via Marathon HTTP API

    http http://mh9-dm-in-elasticl-8o235kczv1jx-1273189503.us-west-2.elb.amazonaws.com/service/marathon/v2/apps | python -mjson.tool


## Marathon in DCOS

    dcos marathon app add marathon-private-registry.json
    dcos marathon app list
