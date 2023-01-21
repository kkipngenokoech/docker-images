# docker-images

## example of images

1. Alpine
2. busybox
3. node
4. ubuntu
5. Nginx
6. python postgres

## image and container

A container is a runtime instance of an image.

you can edit images on the containers

## docker-image commands

### sudo docker images

lists all images

### sudo docker image ls

also lists all images

### sudo docker image rm <image-id>

deletes a specific image

### sudo docker images prune -a

delete all images that are not linked ito containers

### sudo docker image inspect <image-id>

find out more information about an image

### sudo docker image history <image-id>

tells us the history about the layers that were built when the images were created

## layering in docker

