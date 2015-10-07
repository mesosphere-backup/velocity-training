# Container & Docker 101

http://www.nkode.io/2014/08/24/valuable-docker-links.html


## Setup

Make sure you have your DCOS cluster per group.

    # add key once:
    ssh-add ~/.ssh/mesosphere-training-aws
    # log in with forwarding enabled (so that you can log in from master to one of the slaves)
    ssh -A core@MASTER_IP_ADDRESS

We will carry out the following tasks on the Mesos master instance of the DCOS. It is a CoreOS environment, so Docker native.

## build

    cd $DIR_THAT_CONTAINS_A_DOCKERFILE
    docker build -t $REPO_NAME .

Note: use $USERNAME/$REPO_NAME then you don't need to tag when pushing to the registry.

## push

Make sure the repo exists under https://hub.docker.com/u/mhausenblas/ and then:

    docker images
    REPOSITORY             TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
    m-shop-app             latest              5891be3406d7        19 hours ago        349.8 MB
    ...
    
    docker tag 5891be3406d7 mhausenblas/m-shop-app 
    docker push mhausenblas/m-shop-app

## run
    
    docker run -it 
    docker run -d
    docker ps -a
    docker ps -l
    
## introspection 

    docker exec -it $CONTAINER_ID sh
    docker logs $CONTAINER_ID
    docker inspect $CONTAINER_ID

## clean up

    docker rm $(docker ps -a -q)
    docker rmi $IMAGE_ID

