<!-- To build image -->
docker build -t <image-name> .
docker images

<!-- To run specific Dockerfile -->
docker build -t <image-name> -f <dockerfile-name> .

<!-- To run container -->
docker run --name <container-name> <image-name>

<!-- Container tidy up -->
docker container ls -a | docker ps
docker stop <container-id> or <container-name>
docker rm <container-id> or <container-name>

<!-- For port mapping -->
docker run --name <container-name> -p <host-port>:<container-port> <image-name> 

<!-- To specify volume -->
docker run --name <container-name> -p <host-port>:<container-port> -v $(pwd):/usr/src/app <image-name> 

<!-- To run the container in detach mode -->
docker run --name <container-name> -p <host-port>:<container-port> -d -v $(pwd):/usr/src/app <image-name> 

<!-- Anonymous volume -->
docker run --name <container-name> -p <host-port>:<container-port> -v $(pwd):/usr/src/app -v /usr/src/app/node_modules <image-name> 

<!-- To get into container -->
docker exec -it <container-name> /bin/sh
docker run -it <image-name> /bin/sh

<!-- If container stopped, it'll also remove it -->
docker run -rm <image-name>

<!-- To inspect container -->
docker inspect <container-name>

<!-- To list and create network -->
docker network ls
docker network create <network-name>

docker run --network <network-name> --name <container-name> -d --rm <image-name>

<!-- Named volumes -->
docker run --name <container-name> --network <network-name> -v <volume-name>:/app -d --rm <image-name>

