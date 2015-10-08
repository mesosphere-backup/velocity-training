# Mesos and Marathon 101

https://mesosphere.github.io/marathon/docs/


## Marathon: launch app

    http POST http://mh9-dm-in-elasticl-8o235kczv1jx-1273189503.us-west-2.elb.amazonaws.com/service/marathon/v2/apps < marathon-hello-world.json

## Marathon: list apps

    http http://mh9-dm-in-elasticl-8o235kczv1jx-1273189503.us-west-2.elb.amazonaws.com/service/marathon/v2/apps | python -mjson.tool

## Marathon in DCOS

    dcos marathon app add marathon-peek.json
    dcos marathon app list


## Navigation

1. [Setup](../)
1. [Containers &amp; Docker](../docker)
1. Mesos &amp; Marathon (You Are Here)
1. [Kubernetes](../kubernetes)
1. [Putting It All Together](../piat)