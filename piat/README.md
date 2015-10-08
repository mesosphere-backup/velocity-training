# Putting it all together

## Setup

Coordinates:

    Dashboard: http://
    Master IP:
    Public Slave: http://
    KubeUI: http://.../service/kubernetes/api/v1/proxy/namespaces/kube-system/services/kube-ui/

Follow https://docs.mesosphere.com/services/kubernetes/ to install K8S and `kubectl`and then:

    export KUBERNETES_MASTER=http://.../service/kubernetes/api
    
... with the FQHN being the Dashboard URL from above.

## Tasks

    dcos package list
    dcos marathon app add marathon-gen.json
    kubectl create -f k8s-webserver-pod.json
    kubectl get pods
    kubectl create -f k8s-webserver-service.json
    kubectl get services
    kubectl delete service nginx-service
    kubectl delete pod nginx

## Further resources

- https://mesosphere.com/blog/2015/06/21/web-application-analytics-using-docker-and-marathon/
- https://github.com/mhausenblas/ntil
- http://kubernetes.io/v1.0/docs/design/architecture.html
- https://github.com/kubernetes/kubernetes/blob/release-1.0/contrib/mesos/docs/architecture.md
- https://github.com/jeffmendoza/kubernetes/blob/gh-pages/solutions/mesosphere.md


## Navigation

1. [Setup](../)
1. [Containers &amp; Docker](../docker)
1. [Mesos &amp; Marathon](../mesos-marathon)
1. [Kubernetes](../kubernetes)
1. Putting It All Together (You Are Here)