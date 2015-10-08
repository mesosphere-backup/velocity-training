# Container & Docker 101

http://www.nkode.io/2014/08/24/valuable-docker-links.html

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


## Navigation

1. [Setup](../README.md)
1. Containers &amp; Docker (You Are Here)
1. [Mesos &amp; Marathon](../mesos-marathon)
1. [Kubernetes](../kubernetes)
1. [Putting It All Together](../piat)
