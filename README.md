# PRISM Docker Implementation
 
- Source: [https://hub.docker.com/r/mseve/prism](https://hub.docker.com/r/mseve/prism)

Docker image for the stochastic model checker PRISM. A binary image can be downloaded from the Docker Hub with the following command:

```sh
docker pull mseve/prism 
```

The PRISM graphical interface can be loaded by running:

```sh
docker run -e DISPLAY \
           -v /tmp/.X11-unix:/tmp/.X11-unix \
           -v $HOME/.Xauthority:/home/prism/.Xauthority \
           --net=host 
           -i -t mseve/prism \
           xprism   
```

## Load Current Directory

```sh
PRISM_DOCKER="mseve/prism"
docker run -it --rm --mount src=$(pwd)/,target=/home/prism,type=bind $PRISM_DOCKER /bin/bash
```