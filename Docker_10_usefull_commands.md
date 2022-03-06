# Welcome to TechPark repository!

To learn more about IT world and DevOps, subscribe my channel  [**TechPark**](https://www.youtube.com/channel/UClM-3NJDYp8GKMlQ0tgIjUg) 

 

## Docker tutorial series video number 4 (Top 10 docker commands You must know)
### youtube video [**link**](https://youtu.be/vSMd1uqc2RU)
###
 
 
### Play with Docker
you can use your local machine or online [**play with docker**](https://labs.play-with-docker.com/) tool for practising the command 



### Run a container
#### $docker run [OPTIONS] CONTAINER COMMAND [ARG...]


Run a nginx container 

```
docker run nginx
```
Run docker container in background 
```
docker run -d nginx
```
run docker with container with interactive shell mode 
```
docker run -it nginx bash
```

### Start or stop container
####  docker start/stop [OPTIONS] CONTAINER [CONTAINER...]
 Stop a running container
 ```
 docker stop <container id/name>
 ```
 
 ### List docker images 
 
 #### docker images [OPTIONS] [REPOSITORY[:TAG]]
  ```
  docker images
  ```
  list all images 
   ```
  docker images -a
  ``` 
  ### Pull docker images 
 ####  docker pull [OPTIONS] NAME[:TAG|@DIGEST]
 ```
 docker pull redis 
 ```
 ### Delete docker image 
 ####  docker rmi [OPTIONS] IMAGE [IMAGE...]
 ```
 docker rmi nginx
 ```
 
 ### List docker containers
 ####  docker ps [OPTIONS]
 List running containers
 ```
 docker ps
 ```
 List all container included non running containers
 ```
 docker ps -a
 ```
 List only Ids of running containers 
 ```
 docker ps -q
 ```
  List only Ids of all the containers 
  ```
   docker ps -qa
  ```
 
 ### Kill running container 
 #### docker kill [OPTIONS] CONTAINER [CONTAINER...]
 ````
 docker kill <container Id>
 ````
  ### Remove running or stopped container permanently 
 ####  docker rm [OPTIONS] CONTAINER [CONTAINER...]
 ```
 docker rm <Container ID>
 ```
 ### Run commands on already running container or get shell access 
 ####  docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
 Take shell access of a running container 
 
 ```
 docker exec -it <Container ID>  bash
 #or
 docker exec -it <Container ID> sh
 #or
 docker exec it <Container ID> /bin/bash
 #or
 docker exec it <Container ID> /bin/sh
 ```
 Execute command on a running container 
 ```
 docker exec <Container ID> ls -lht
 ```
 
 ### Create a new image from a container
 ####  docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
 ```
 docker commit <Container Id> custom-image 
 ```
