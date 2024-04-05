#### clean_podman_docker_guide
also see: https://github.com/lineality/podman_docker_cheatsheet/

# Clean Up: Remove Old Container Files

Podman vs. Docker Rule of Thumb -> "docker" -> "podman" 

#### Reference: One of the few extensive accurate lists:
https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/


# Podman
'sudo' not needed using fedora linux

## Quick Clean
```
podman images -q | xargs -r podman rmi -f
```

## Check if docker is still using memory in any area:
```
podman system df
```

## Remove Old Files (optional)
```
podman system prune; podman image prune; podman volume prune; podman container prune
```

## for images that refuse to be deleted...
```
podman images
```
Then number-id of images in here (in place of '#'):
```
$ podman rmi # # # --force 
```





# Docker 
"sudo" maybe needed in ubuntu


## for images that refuse to be deleted...
```
$ docker images
```
Then number-id of images in here (in place of '#'):
```
$ sudo docker rmi # # # --force 
```

## Check if docker is still using memory in any area:
```
$ sudo docker system df
```

## Remove Old Files (optional)
```
$ sudo docker system prune; sudo docker image prune; sudo docker volume prune; sudo docker container prune
```

## Quick Clean
```
sudo docker images -q | xargs -r sudo docker rmi -f
```
