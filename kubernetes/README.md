# Kubernetes 101

Keep http://kubernetes.io/v1.0/ somewhere open.


## Install Kubernetes

Follow the instructions in https://docs.mesosphere.com/services/kubernetes/ to install Kubernetes:

    $ dcos config prepend package.sources https://github.com/mesosphere/multiverse/archive/version-1.x.zip
    $ dcos package update --validate
    $ dcos package install kubernetes

... and then `kubectl` from there as well. Once you have Kubernetes as a service installed and `kubectl` the CLI on your local laptop, do:

    export KUBERNETES_MASTER=http://.../service/kubernetes/api
    
... with the FQHN being the Dashboard URL from above.


## Kubernetes 101

    $ kubectl run mh9-nginx --image=nginx --replicas=2 --port=80
    $ kubectl get pods
    $ kubectl delete rc mh9-nginx
