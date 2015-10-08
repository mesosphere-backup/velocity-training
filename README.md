# Container management with Docker and Kubernetes

Training session at Velocity NYC, 2015, see also http://velocityconf.com/devops-web-performance-ny-2015/public/schedule/detail/44830

## Setup

Each group should have a DCOS cluster.

1. Download the ssh key
1. Add the key to your keychain

  ```
  ssh-add ~/.ssh/mesosphere-training-aws
  ```
1. Log into the DCOS master node with key forwarding enabled (to allow logging into slaves)

  ```
  ssh -A core@MASTER_IP_ADDRESS
  ```

The DCOS master node is a CoreOS environment, with minimal developer tools but built-in docker.
It is also the node on which mesos-master and marathon are running.


## Navigation

1. Setup (You Are Here)
1. [Containers &amp; Docker](./docker)
1. [Mesos &amp; Marathon](./mesos-marathon)
1. [Kubernetes](./kubernetes)
1. [Putting It All Together](./piat)
