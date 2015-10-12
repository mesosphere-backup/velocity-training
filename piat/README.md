# Putting it all together

## Setup

Fill in with your own coordinates:

    Dashboard: http://
    Master IP:
    Public Slave: http://
    KubeUI: http://$DCOS_DASHBOARD_FQHN/service/kubernetes/api/v1/proxy/namespaces/kube-system/services/kube-ui/

## Example: a hybrid workload

    $ dcos package list
    $ dcos marathon app add ./marathon-gen.json
    $ kubectl create -f ./k8s-webserver-pod.json
    $ kubectl get pods
    $ kubectl create -f ./k8s-webserver-service.json
    $ kubectl get services
    $ kubectl delete service nginx-service
    $ kubectl delete pod nginx

## Further resources

- https://mesosphere.com/blog/2015/06/21/web-application-analytics-using-docker-and-marathon/
- https://github.com/mhausenblas/ntil
- http://kubernetes.io/v1.0/docs/design/architecture.html
- https://github.com/kubernetes/kubernetes/blob/release-1.0/contrib/mesos/docs/architecture.md
- https://github.com/jeffmendoza/kubernetes/blob/gh-pages/solutions/mesosphere.md
